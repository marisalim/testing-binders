# testing-binders

Click on the badge to open binder. It may take a few minutes to load:

[![Binder](https://binder.pangeo.io/badge_logo.svg)](https://binder.pangeo.io/v2/gh/marisalim/testing-binders/stable-binder)



## Building a Pangeo binder

### Step 1: Make a Github repo

### Step 2: add binder environment files

On `main` branch, add all the files you want for binder in `./binder/`.

Once you're done, make branch to point pangeo to so that it doesn't get accidentally changed (e.g., `stable-binder`)

### Step 3: Open pangeo

Go to: https://binder.pangeo.io/

Fill in `Github repository name or URL` and `Git branch, tag, or commit`. 

Copy/paste the binder badge to the Github repo README.md (if you wait to get the badge after the binder is done building, it will go to the JupyterLab and you may have to navigate back to the pangeo binder page to get it).

![](https://i.imgur.com/L8v0Zbm.png)

Launch:

![](https://i.imgur.com/HsOifLH.png)


Building takes a while:

![](https://i.imgur.com/Mb6dFqi.png)

binder is building an image. then it will push the image:

![](https://i.imgur.com/3WI7uvf.png)

After launch is complete, the binder will open as a JupyterLab page. 

### Test commands in the binder

Click on 'Terminal' 

Enter command line commands. `nano` should be installed. 

Try to build conda environment:

```
# create conda environment
conda env create -n learnconda -f ./binder/environment.yml

# activate conda environment
conda activate learnconda

# download a fastq file to run in FastQC
wget https://osf.io/4rdza/download -O SRR2584857_1.fastq.gz
gunzip SRR2584857_1.fastq.gz 

# run FastQC (if there is no input file, fastqc will give a X11 DISPLAY error
fastqc SRR2584857_1.fastq 
```

commands with screen outputs:
```
(learnconda) jovyan@jupyter-marisalim-2dtesting-2dbinders-2d47sgv8r0:~$ fastqc
Exception in thread "main" java.awt.HeadlessException: 
No X11 DISPLAY variable was set, but this program performed an operation which requires it.
        at java.desktop/java.awt.GraphicsEnvironment.checkHeadless(GraphicsEnvironment.java:208)
        at java.desktop/java.awt.Window.<init>(Window.java:548)
        at java.desktop/java.awt.Frame.<init>(Frame.java:423)
        at java.desktop/java.awt.Frame.<init>(Frame.java:388)
        at java.desktop/javax.swing.JFrame.<init>(JFrame.java:180)
        at uk.ac.babraham.FastQC.FastQCApplication.<init>(FastQCApplication.java:63)
        at uk.ac.babraham.FastQC.FastQCApplication.main(FastQCApplication.java:338)
(learnconda) jovyan@jupyter-marisalim-2dtesting-2dbinders-2d47sgv8r0:~$ wget https://osf.io/4rdza/download -O SRR2584857_1.fastq.gz
--2021-01-15 00:51:25--  https://osf.io/4rdza/download
Resolving osf.io (osf.io)... 35.190.84.173
Connecting to osf.io (osf.io)|35.190.84.173|:443... connected.
HTTP request sent, awaiting response... 302 FOUND
Location: https://files.osf.io/v1/resources/vzfc6/providers/osfstorage/5e17f8767545840323fa2ec0?action=download&direct&version=1 [following]
--2021-01-15 00:51:26--  https://files.osf.io/v1/resources/vzfc6/providers/osfstorage/5e17f8767545840323fa2ec0?action=download&direct&version=1
Resolving files.osf.io (files.osf.io)... 35.186.214.196
Connecting to files.osf.io (files.osf.io)|35.186.214.196|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8706066 (8.3M) [application/octet-stream]
Saving to: ‘SRR2584857_1.fastq.gz’

SRR2584857_1.fastq.gz              100%[==============================================================>]   8.30M  25.8MB/s    in 0.3s    

2021-01-15 00:51:28 (25.8 MB/s) - ‘SRR2584857_1.fastq.gz’ saved [8706066/8706066]

(learnconda2) jovyan@jupyter-marisalim-2dtesting-2dbinders-2d47sgv8r0:~$ ls
binder  README.md  SRR2584857_1.fastq.gz
(learnconda2) jovyan@jupyter-marisalim-2dtesting-2dbinders-2d47sgv8r0:~$ gunzip SRR2584857_1.fastq.gz 
(learnconda2) jovyan@jupyter-marisalim-2dtesting-2dbinders-2d47sgv8r0:~$ fastqc SRR2584857_1.fastq 
Started analysis of SRR2584857_1.fastq
Approx 5% complete for SRR2584857_1.fastq
Approx 10% complete for SRR2584857_1.fastq
Approx 15% complete for SRR2584857_1.fastq
Approx 20% complete for SRR2584857_1.fastq
Approx 25% complete for SRR2584857_1.fastq
Approx 30% complete for SRR2584857_1.fastq
Approx 35% complete for SRR2584857_1.fastq
Approx 40% complete for SRR2584857_1.fastq
Approx 45% complete for SRR2584857_1.fastq
Approx 50% complete for SRR2584857_1.fastq
Approx 55% complete for SRR2584857_1.fastq
Approx 60% complete for SRR2584857_1.fastq
Approx 65% complete for SRR2584857_1.fastq
Approx 70% complete for SRR2584857_1.fastq
Approx 75% complete for SRR2584857_1.fastq
Approx 80% complete for SRR2584857_1.fastq
Approx 85% complete for SRR2584857_1.fastq
Approx 90% complete for SRR2584857_1.fastq
Approx 95% complete for SRR2584857_1.fastq
Approx 100% complete for SRR2584857_1.fastq
Analysis complete for SRR2584857_1.fastq
(learnconda) jovyan@jupyter-marisalim-2dtesting-2dbinders-2d47sgv8r0:~$ ls
binder  README.md  SRR2584857_1.fastq  SRR2584857_1_fastqc.html  SRR2584857_1_fastqc.zip
```







