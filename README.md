# singularity-slurm-base
Run Slurm commands inside a Singularity container that will execute against the host Slurm deployment.

## Basic Usage
```
singularity image.create slurm-base.img
singularity build slurm-base.img Singularity
singularity shell --cleanenv --bind /home/slurm --bind /var/run/munge --bind /etc/slurm slurm-base.img
```

## Notes
* Users not in the image's `/etc/passwd` file will be resolved as nobody when running Slurm commands.
