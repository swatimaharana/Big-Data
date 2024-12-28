* Version : shows the version of hadoop installed.       
    * hadoop version 

* Mkdir: takes the path as an argument and creates a directory. 
    * hdfs dfs -mkdir /user/dataflair/dir1 

* Ls : displays the content of the directory specified by path. 
    * hdfs dfs -ls /user/dataflair 

* Put : This command copies the file in the local filesystem to the file in DFS. 
    * hdfs dfs -put /home/sample.txt /user/dataflair/dir1 

* CopyFromLocal:  This command is similar to put command. But the source should refer to local file. 
    * hdfs dfs -copyFromLocal /home/sample /user/dataflair/dir1 

* Get : This command retrieves all files in the source path entered by the user in HDFS. And merges them into one single file created in the local file system identified by local destination. 
    * hdfs dfs -get /user/dataflair/dir1 /home 
    * hdfs dfs -getmerge /user/dataflair/dir1/sample.txt /user/dataflair/dir2/sample2.txt /home/sample1.txt 
    * hadoop fs –getfacl -R /user/dataflair/dir1  
        (Access Control Lists (ACLs) of files and directories) 
    * hadoop fs –getfattr –d /user/dataflair/dir1 
        (Recursive Access Control Lists (ACLs) of files and directories) 
    * hadoop fs –getfattr –d /user/dataflair/dir1 
        (This HDFS command displays if there is any extended attribute names and values for the specified file or directory) 

* CopyToLocal :  
    * It is similar to get command. Only the difference is that in this the destination of copied file should refer to a local file. 
    * hdfs dfs -copyToLocal /user/dataflair/dir1 /home 

* Cat :  displays the contents of file on console or stdout. 
    * hdfs dfs -cat /user/dataflair/dir1/sample.txt 

* Mv : moves the file from the specified source to destination within HDFS.  
    * hdfs dfs -mv /user/dataflair/dir1/sample.txt /user/dataflair/dir2 

* CP : Copies the file or directory from given source to destination within HDFS. 
    * hdfs dfs -cp /user/dataflair/dir2/sample.txt /user/dataflair/dir1 

* Getmerge:  
    * getmerge command is used to merge multiple files in an HDFS(Hadoop Distributed File System) and then put it into one single output file in our local file system. 
    * hdfs dfs -getmerge /user/dataflair/dir1/sample.txt /user/dataflair/dir2/sample2.txt /home/sample1.txt 

* copyFromLocal:  
    * copy the file from the local file system to Hadoop Distributed File System (HDFS) 
    * hdfs dfs –copyFromLocal <local-source> URI 
    * hdfs dfs –copyFromLocal -f  <local-source> URI 

* To List the partitions. 
    * hive -e show partitions table_name; 

Hdfs fsck /data/file1 -blocks –locations –files 