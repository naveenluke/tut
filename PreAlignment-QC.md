![RNA-seq Flowchart - Module 1](Images/RNA-seq_Flowchart2.png)

# 1-vi. Pre-Alignment QC

You can use FastQC to get a sense of your data quality before alignment:
* http://www.bioinformatics.babraham.ac.uk/projects/fastqc/

Video Tutorial here: 
* http://www.youtube.com/watch?v=bz93ReOv87Y

Try to run FastQC on your fastq files:

```bash

cd $RNA_HOME/data
fastqc *.fastq.gz

```

Then, go to the following url in your browser:
* http://__YOUR_DNS_NAME__/workspace/rnaseq/data/
* Note, you must replace __YOUR_DNS_NAME__ with your own amazon instance DNS (e.g., ec2-54-187-159-113.us-west-2.compute.amazonaws.com))
* Click on any of the `*_fastqc.html` files to view the FastQC report

### Exercise

Investigate the source/explanation for over-represented sequences:
- HINT: Try BLASTing them.

---
## PRACTICAL EXERCISE 4

Assignment: Run FASTQC on one of the additional fastq files you downloaded in the previous practical exercise. 

* Hint: Remember that you stored this data in a separate working directory called ‘practice’.

Run FASTQC on the file 'hcc1395_normal_1.fastq.gz' and answer these questions by examining the output.

**Questions**
* How many total sequences are there?
* What is the range (x - y) of read lengths observed?
* What is the most common average sequence quality score?
* What does the Adaptor Content warning tell us?

Solution: When you are ready you can check your approach against the [Solutions](https://github.com/griffithlab/rnaseq_tutorial/wiki/Solutions#practical-exercise-4---data-qc)

---

Run MultiQC on your fastqc reports to generate a single summary report across all samples/replicates.

```bash

cd $RNA_HOME/data
multiqc .

```


---

| [[Previous Section\|RNAseq-Data]] | [[This Section\|PreAlignment-QC]]    | [[Next Section\|Adapter-Trim]] |
|:--------------------------------:|:-----------------------------------:|:--------------------------:|
| [[Data\|RNAseq-Data]]             | [[Data QC\|PreAlignment-QC]]         | [[Adapter Trim\|Adapter-Trim]]    |
