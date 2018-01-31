# singularity-slurm-base
Run Slurm commands inside a Singularity container that will execute against the host Slurm deployment.

## Basic Usage
```
singularity image.create slurm-base.img
singularity build slurm-base.img Singularity
singularity shell --cleanenv --bind /var/lib/sss/pipes --bind /home/slurm --bind /var/run/munge --bind /etc/slurm slurm-base.img
```

## Notes
* SSSD is now installed in the container, so the behavior of the host nsswitch will be maintained.
* For multiuser services, it may be necessary to mount /home.
