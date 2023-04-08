ChatGPT answers:
3. 
Prompt: Help me create a new folder in Hadoop (not in the local filesystem)
Answer: hadoop fs -mkdir /path/to/new/folder

The answer is correct.

4.
Prompt: Move one file that you have just uploaded to Wolf to the new folder in Hadoop
Answer: hadoop fs -put /path/to/local/file /path/to/hdfs/folder

The answer is correct.

5.	
Prompt: Rename this file in Hadoop
Answer: hadoop fs -mv /path/to/current/hdfs/file /path/to/new/hdfs/file

The answer is correct.

6.	
Prompt: Copy this file from Hadoop to the local filesystem.
Answer: hadoop fs -get /path/to/hdfs/file /path/to/local/destination
or hadoop fs -copyToLocal /user/your_username/new_folder/renamed_file.txt /Users/your_local_username/Desktop/renamed_file.txt

The answer is correct. I used the second method "copyToLocal" suggested by ChatGPT. 

7.	
Prompt: Create a second folder in Hadoop. Copy two small text files to it. Then extract from Hadoop a single file that is going to be the concatenation of the two files, i.e., appending one file to the other one. (use getmerge)
Answer: 
hadoop fs -mkdir /user/your_username/second_folder
hadoop fs -put /path/to/local/text_file1.txt /user/your_username/second_folder/text_file1.txt
hadoop fs -put /path/to/local/text_file2.txt /user/your_username/second_folder/text_file2.txt
hadoop fs -getmerge /user/your_username/second_folder /path/to/local/merged_file.txt

The answer is correct, and slightly different than my answer. ChatGPT uses "put" command to copy two text files from local filesystem to Haddop, while I used the "copyFromLocal" method. 

8.	
Prompt: Take a different file on your local filesystem, move it to Hadoop, and then within Hadoop copy the same file to Tucker’s folder (/user/tlewis). 
Answer: 
hadoop fs -copyFromLocal /path/to/local/file /path/to/hdfs/destination
hadoop fs -cp /path/to/current/hdfs/file /path/to/new/hdfs/file

It returns a "Permission denied" error message, but the answer should be correct given the permission. 
