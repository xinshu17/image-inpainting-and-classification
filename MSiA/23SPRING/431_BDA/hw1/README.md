1.	Connect to Wolf through putty (or plain ssh on a mac or linux) 

2.	Ftp a few files from your local laptop to Wolf (on windows use filezilla, on mac use sftp or Cyberduck)

3.	Create a new folder in Hadoop (not in the local filesystem)

hdfs dfs -mkdir MSiA_431_hw1

4.	Move one file that you have just uploaded to Wolf to the new folder in Hadoop

hadoop fs -put test_file.txt MSiA_431_hw1

5.	Rename this file in Hadoop

hadoop fs -mv hw1/test_file.txt hw1/new_file.txt

6.	Copy this file from Hadoop to the local filesystem.

hdfs dfs -copyToLocal MSiA_431_hw1 MSiA_431_hw1_local

7.	Create a second folder in Hadoop. Copy two small text files to it. Then extract from Hadoop a single file that is going to be the concatenation of the two files, i.e., appending one file to the other one. (use getmerge)

hdfs dfs -mkdir MSiA_431_hw1_2
hdfs dfs -copyFromLocal file1.txt MSiA_431_hw1_2/file1.txt
hdfs dfs -copyFromLocal file2.txt MSiA_431_hw1_2/file2.txt
hdfs dfs -getmerge MSiA_431_hw1_2/ file_merge.txt

8.	Take a different file on your local filesystem, move it to Hadoop, and then within Hadoop copy the same file to Tucker’s folder (/user/tlewis). 

hdfs dfs -copyFromLocal xinshu.txt MSiA_431_hw1_2
hdfs dfs -cp MSiA_431_hw1_2/xinshu.txt /user/tlewis

cp: Permission denied: user=xst2267, access=WRITE, inode="/user":hadoopuser:supergroup:drwxr-xr-x

