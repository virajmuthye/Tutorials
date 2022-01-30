## Using the SLURM scheduler on ARC

ARC cluster is a collection of several compute nodes connected by a high-speed network. On ARC, computations get submitted as jobs. Once submitted, the jobs are then assigned to compute nodes by the job scheduler as resources become available.

The job scheduling system on ARC is called SLURM.

Take a look at SLURM basics here:https://researchit.las.iastate.edu/slurm-basics

### Main Slurm Commands
sbatch - submit a job script.
srun - run a command on allocated compute node(s).
scancel - delete a job.
squeue - show state of jobs.

You will use SLURM to do most of your work for this project. 
In this tutorial you will  submit your first SLURM job.

### Step 1. Log in to ARC

### Step 2. Navigate to /work/wasmuth_lab/rida

### Step 3. Copy all files from /work/wasmuth_lab/viraj/slurm_tutorial in this directory

### Step 4. Run the SLURM job 
```markdown
	 sbatch blastp.slurm
```

You should see this line on the terminal 
  ```markdown
     Submitted batch job <JOB ID>"
	```  
  This is the JOB ID.
	In case you need to track or delete your job, you will need it.

### Step 5. Run the SLURM comman
```markdown
   squeue rida.mahmood1	
```
	Now, you should be able to see the JOB ID and the status of the job.
	The status of the job is under the column "ST". If it says "R" it means that the job is running.
	
### Wait for the job to finish.

	If you give the command "squeue rida.mahmood1" and do not see a job in the list, then either the job as finished or there was an error.
	If there was an error in running the script, you should see it in the "job.error" file.

The results will be in the file "all_control.db.pep.pfal.results"

Answer the following questions
------------------------------
1. Did you get any emails from ARC? 
   What information was in those emails?

2. Aftering submitting the job, what was the ID?
   How can you find out the JOB ID?

3. After the job finishes running, check the contents of the "job.error" and "job.output" files.
