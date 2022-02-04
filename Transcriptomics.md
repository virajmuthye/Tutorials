## Let's assemble a transcriptome!

**Create a directory in your work directory (/work/wasmuth_lab/rida) called trinit*
**Go inside that folder**
**Type the following commands to install Trinity**

```markdown
module load bioconda/conda3
conda create -n trinity
source activate trinity
conda install -c bioconda trinity
```

**Wait for the commands to run.**
**Then type the following command**

```markdown
source deactivate trinity
```

### Congratulations! You have now installed Trinity :)

**Next, copy the following files from "/work/wasmuth_lab/viraj/trinity_tutorial"**

```markdown
left reads : SRR1557039_1_trimmomatic.fastq
right reads : SRR1557039_2_trimmomatic.fastq
trinity SLURM job script: trinity_rida.slurm
```

**Now, check out the trinity_rida.slurm.** 
**What changes do you need to make?**
**Once you have made the changes, message me the script on slack!**

**Now, after checking with me, submit the SLURM job script.**

### Well done! You have now started assembling your very first transcriptome :)

