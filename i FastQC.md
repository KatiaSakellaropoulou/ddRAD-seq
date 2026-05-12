We can check just some files R1 and R2 to check if the sequencing per base quality is okay.
We also check one or two files after the trimmomatic to make sure that the adapters are gone and everything looks good.

We need to check for the quality of our reads. Since we have lots of PE reads, we can create a script with a loop

```
#fastqc loop

#PBS -N fastqc_loop
#PBS -l select=1:ncpus=2:mem=30gb:scratch_local=30gb
#PBS -l walltime=03:00:00

input_dir="/storage/brno2/home/kat/Lim3_fastq"
output_dir="/storage/brno2/home/kat/fastqc_analysis/fastqc_loop"

module add fastQC-0.11.5

for file in $input_dir/*.fq.gz; do
    echo "Running FastQC on $file"
    fastqc -o $output_dir $file
done
```
