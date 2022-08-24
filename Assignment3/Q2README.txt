1. The dataset that I used can be download from this link: https://snap.stanford.edu/data/ego-Twitter.html 
2. The program has two type of arguments: input path, and output path. Arguments save in .csv file. Before run the code, upload argument file to Databricks. Don't forget to install graph-frame package. Then run the code directly. 
3. The input file stored in S3 bucket. I do try to output the file to S3, but its too slow, I need to wait more than an hour. So my solution is to save .csv file to databrick, then you can read the file, download directly, it's quicker, but still slow.

