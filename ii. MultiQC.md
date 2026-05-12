
After the FASTQC, the next step is to use multifastqc to have them all in one report.
```
#MULTIQC this needs to be done one by one and not on job. 
module add mambaforge && mamba env list
module add mambaforge
mamba activate multiqc_v1.12_py3.7
mamba deactivate
```
