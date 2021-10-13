# Let's learn some Linux!
## This is a very basic tutorial. If you have any suggestions or questions, please email me at virajrajendra.muthye@ucalgary.ca
## A lot of this information has been taken from a tutorial provided by Kaylee Rich in the Wasmuth Lab at the University of Calgary.

## Let's begin!

A few things to know before you begin-
In Linux, a "folder" is called a "directory".
A "path" to the directory tells you the location of that directory. 
Every file and directory has a path, which you can navigate through various commands.

This is how the file system is set up-

Let's take a look at this folder "work/wasmuth_lab/viraj/mimicry"
work/
    ---wasmuth_lab/
        ---viraj/
          ----mimicry/ 

The "absolute path" of the folder "mimicry" is "work/wasmuth_lab/viraj/mimicry".
Absolute paths are quite useful!
No matter where you are on ARC, you can reach this folder by typing "cd /work/wasmuth_lab/viraj/mimicry"

You do not always have to use absolute paths.
Sometimes you would prefer a "relative" path.
A "relative" path is a path that tells you how to go to a folder from where you are in the file system.
For instance, if you are in the folder "wasmuth_lab", you can go to the "mimicry" folder by typing "cd viraj/mimicry".

```markdown
Using these commands, a user would be able to :
	Navigate to the folder of interest
	Create a directory for analysis
	Copy files into the newly created directory
	Copy/delete/move files if needed from one directory to another
	Concatanate reads from multiple files into one file
```

## First, take a look at where you are in the maze of directories on ARC
## Type "pwd" and see what happens!

## 1. cd
### The cd command changes the current (working) directory.

```markdown
Command		Effect
cd		Changes to you home directory.
cd foo		Changes to the "foo" directory.
cd ..		Moves up one directory
```

e.g.

Let's say you are in the folder /work/wasmuth_lab

	1. To go to /work/wasmuth_lab/trial :  cd trial
	
	2. To go to /home	      :  cd ..
	
	3. To go to /work/wasmuth_lab/viraj/mimicry      :  cd /work/wasmuth_lab/viraj/mimicry
	
	
## Now, find a folder and lets start copying stuff!
## 2. cp
### The cp command copies files and directories.

```markdown
Command						Effect
cp src-file dest-file		Creates a copy of the file src-file named dest-file.
cp src-file dest-dir		Copies the file src-file into the dest-dir directory.
cp -R src-dir dest-dir		Copies all files and subdirectories within the src-dir directory into the dest-dir directory (The -R stands for "recurisive").
cp -i src dest			Copies the file/directory src to the file/directory dest, but prompts if any files or directories would be overwritten (The -i stands for "'interactive").
cp *.fasta dest-dir         	Copies all files with a fasta extension into the dest-dir directory.
```

e.g.

Let's say you are in the folder work/wasmuth_lab/trial

There are three files in the folder : 1] trial.txt, 2] tutorial.txt, 3] species.fasta

	1. To make a copy of the file "trial.txt" in the same folder	     	: cp trial.txt trial2.txt
	
	2. To make a copy of the file "trial.txt" in the folder /work/wasmuth_lab/viraj/mimicry	: cp trial.txt /work/wasmuth_lab/viraj/mimicry.
	
	3. To copy all files with the extension *.txt to folder /work/wasmuth_lab/viraj/mimicry	: cp *.txt /work/wasmuth_lab/viraj/mimicry.
	

## Now, how would you know what all is there in this folder?
## 3. ls
### The ls command lists directory contents.

```markdown
Command			Effect
ls			Lists the contents of the current working directory.
```

## Enough copying, let's now CREATE a directory!
## 4. mkdir
### The mkdir command makes (i.e. creates) a new directory.

```markdown
Command			Effect
mkdir foo		Creates a new directory named foo.
```

Make a folder with any name of your choice.
But!
Be careful of how you name directories and files. Avoid spaces in file and directory names.

 ## 5. mv
### The mv command moves or renames files and directories.

```markdown
Command					      Effect
mv old-file new-file		Renames the file old-file to new-file
mv src-file dest-dir		Moves the file src-file into the dest-dir directory.
mv old-dir new-dir		Renames the old-dir directory to new-dir.
mv -i src dest			Moves or renames src to dest, but prompts if any files or directories would be overwritten (The -i stands for "interactive").
```

e.g.

Let's say you are in the folder /home/viraj/

There is three files in the folder : 1] trial.txt, 2] tutorial.txt, 3] species.fasta

	1. To rename the file trial.txt to new.txt : mv trial.txt new.txt
	
	2. To move trial.txt to /bin/lavrov/   	   : mv trial.txt  /bin/lavrov/
	



# 6. rm 
### Be very careful with this command, there is no way to reverse this!
### For a scary story, google "rm command and Toy Story"
### The rm command removes (i.e. deletes) files. (To remove directories, see the rmdir command below.)

```markdown
Command					Effect
rm foo					Deletes the file foo.
rm -r dir				Deletes the foo directory, including all of its files and subdirectories (The -r stands for "recursive"). 
rm -i file				Deletes the file foo, but prompts before actually deleting it (The -i stands for "interactive").
```


## 7. rmdir
### The rmdir command removes empty directories.

```markdown
Command					Effect
rmdir foo				Deletes the foo directory, only if it is empty.
```


## 8. cat
### cat command allows us to create single or multiple files, view contain of file, concatenate files and redirect output in terminal or files.

```markdown
Command					Effect
cat foo					Displays the content of file "foo1" 
cat foo1 foo2				Concatanates the contents of the two files "foo1" and "foo2"
```

e.g.

Let's say you are in the folder /home/viraj/

There is four files in the folder : 1] trial.txt, 2] tutorial.txt, 3] species.fasta, 4] sponges.fasta

	1. To concatanate content from both fasta files 					: cat species.fasta sponges.fasta
	
	2. To create a new file (newfile.fasta) containing content from both fasta files 	: cat species.fasta sponges.fasta > newfile.fasta
	
	3. To concatanate content of all files with *.fasta extension				: cat *.fasta
	



# Submitting and managing jobs on Condo using SLURM



The job script will contain Slurm settings, such as number of cores and time requested, and the commands that should be executed during the batch session.

Use Slurm Job Script Generator for Condo to create job scripts.

It is good practice to maintain a consistent file extension like ".slurm" to keep track of slurm job scripts.


```markdown
To submit the job 	: sbatch <job_script>
To see the job queue	: squeue - u <net-id>  e.g. squeue -u vrmuthye
To cancel the job 	: scancel <job_id>
```
	
For more details, check : https://www.hpc.iastate.edu/guides/condo-2017/managing-jobs-using-slurm-workload-manager

The SLURM job creator   : https://www.hpc.iastate.edu/guides/condo-2017/slurm-job-script-generator-for-condo



# Few important commands:


1. Counting number of sequences in a FASTA file

```markdown
grep ">" FILE | wc -l
```

2. Count the number of lines in a file
```markdown
wc -l FILE
```

3. Write the first X lines of file to screen
```markdown
head -10 FILE
```

4. Write the last X lines of a file to the screen
```markdown
tail -10 FILE
```


## You can also practice at https://www.tutorialspoint.com/execute_bash_online.php

## References
### I have taken material from these resources. They have much more information. I highly recommend going through them!
```markdown
http://www.ee.surrey.ac.uk/Teaching/Unix/
https://www.hpc.iastate.edu/guides/unix-introduction/unix-tutorial-1

```

