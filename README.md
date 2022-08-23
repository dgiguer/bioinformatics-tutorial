# Bioinformatics-tutorial

Get the bioinformatics-tutorial.pem file from Slack.

Set working directory to where you saved bioinformatics-tutorial.pem

Change permissions as follow 
```
chmod 400 bioinformatics-tutorial.pem
```

Log into EC2 instance:

```
ssh -i "bioinformatics-tutorial.pem" ec2-user@ec2-52-91-4-173.compute-1.amazonaws.com
```

Once logged in: 

```
# change output files to have your name so you don't overwrite anyone elses file
fastp -i r1-sub.fastq -I r2-sub.fastq -o r1-filt-YOURNAME.fastq -O r2-filt-YOURNAME.fastq–html fastp-report-YOURNAME.html
```

To download results, use a new terminal tab: 

```
scp -i "bioinformatics-tutorial.pem" ec2-user@ec2-52-207-245-28.compute-1.amazonaws.com:/home/ec2-user/fastp-report-YOURNAME.html .
```

Open in browser
