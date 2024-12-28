# Question 1 

1. Create two directories ‘dir1’ and ‘dir2’ using a single hdfs command inside home directory of hdfs in Cloudera VM. The dir2 should be subdirectory of dir1. 

        hadoop fs -mkdir -p /user/cloudera/dir1/dir2  

2. Verify that the two folders have been created in the above path Inside dir 2 

        hadoop fs -ls /user/cloudera/dir1/ 

3. Create an empty file, file1.txt 

        Touch file1.txt 

4. Create a file file2.txt in local filesystem with some text inside it. 
        gedit file2.txt 

5. Copy file2.txt from local to hdfs inside dir2. 

        hadoop fs -copyFromLocal file2.txt /user/cloudera/dir1/dir2 

6. List the subdirectories and files inside dir1 recursively. 

        hadoop fs -ls -R /user/cloudera/dir1/ 

7. List the files inside dir2 ,sorted by size but size should be displayed in KBs/MBs  and not bytes 

        hadoop fs -ls -h -S /user/cloudera/dir1/dir2 

8. Rename the file, file2.txt to file3.txt 

        mv  file2.txt  file3.txt 

9. Remove the directory dir1 using a single command. 

        hadoop fs -rm -R /user/cloudera/dir1/ 


# Question 2 

Suppose there is file of size 514 MB stored in HDFS (Hadoop 2.x) using default block size configuration and default replication factor: 

1. How many blocks will be created in total ? 

        12 

2. What will be the size of each block? 

        128 MB 

# Question 3 

1. Create a directory inside home directory of local filesystem named ‘test’. 

        mkdir test 

2. Create few empty files inside the test directory namely a.pdf, b.html, c.xml 

        touch a.pdf b.html c.xml  

3. List the files in reverse alphabetical order of file name 

4. Display only the file which ends with .html extension 

        ls -lrt *.html 

# Question 4 

1. Create two new text files, file1 and file2 , with following content using cat command in your Linux home directory: 

        file1: This is from file1 
        file2: This is from file2 
        cat > file1 
        This is from file1 ^D 
        cat > file2 
        This is from file2 ^D 

2. Display the contents of the file 1 and file2 using cat command 

        Cat file1 
        Cat file2 

3. Concatenate the contents of the two files and put them into a new file file3 and display the results. 

        Cat file1  >> file3 
        Cat file2 >> file3 
        Cat file3 

4. Count the number of lines and number of words in the file3. 

        wc -l file3 
        wc -w file3 

# Question 5 
Create a text file myfile.txt with 5 lines in home directory of local filesystem: 

1. Display last 3 lines of that file. 

        tail -3 myfile.txt 

2. Display all lines of that text file except first line. 

        tail -4 myfile.txt 

# Question 6 

The getmerge command in Hadoop is for merging files existing in the HDFS file system into a single file in the local file system. 

1. Use the help for getmerge command to see the arguments it takes 

        hadoop fs -help getmerge 
        -getmerge [-nl] <src> <localdst> : 
        Get all the files in the directories that match the source file pattern and 
        merge and sort them to only one file on local fs. <src> is kept. 
        -nl  Add a newline character at the end of each file 

2. Create file1.txt in local with contents “Hello, this is from file1“,  
        Create file2.txt in local with contents “Hello, this is from file2” 
        cat > file2.txt 
        “Hello, this is from file2” 

3. Copy the file1.txt and file2.txt into a hdfs location inside home directory in hdfs 

        hadoop fs -copyFromLocal file1.txt file2.txt /user/cloudera 

4. Use the getmerge command to merge the contents of two files present in hdfs and put the merged content into a single local destination file named filenew.txt. 

        hadoop  fs -getmerge /user/cloudera/file1.txt /user/cloudera/file2.txt /home/cloudera/filenew.txt 

5. Display the merged contents of the file filenew.txt 

        cat filenew.txt 
        “Hello, this is from file1“ 
        “Hello, this is from file2” 