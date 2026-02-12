# Storage


The need for storing large amount of data has exploded in recent years. The legal archiving requirements are as follows:

- *Ten years* after the last use in a publication by the authors who generated the data. 

- *Fifteen years* for drug trials 

- *Seventeen years* for EU grants

This placed a huge burden on individual research groups and on the required infrastructure. To limit manpower and maintenance costs, it was agreed during the UPSC board meeting in 2023 that a central storage should be purchased and administered by the UPSC bioinformatics facility.
Upon reviewing alternatives, the cheapest option was selected and will be financed through user fees, i.e. research groups will pay a fee (1.5 SEK / GB /year) for their allocated storage.


## Purpose

The storage is meant to store research data of any kind, at the moment principally `sequencing` and `microscopy`. However, the storage can also be used at the discretion of the research groups to store and share additional research- or work-related data. While, this may seem redundant to the existing access to storage solutions from either university (SLU or UmU) (e.g. OneDrive), it may be easier to use for storing data generated on instruments in the lab, where the storage can be readily accessible, such as the case for the computers associated to the microscopes.

In additon to the time requirements mentioned above, safe data storage also puts emphasis on storing at least 3 copies of data, in two different formats, and at two different physical locations out of which ideally one should be offline (3-2-2-1). Having the data on our storage server allows you to be in partial compliance with these regulations. 

## Specifications

The storage is hosted on a Synology NAS HD6500 with currently 501 TB of storage. This is named `hopper`. It is extensible to 6 PB through extension units (1PB each). The storage is redundant (RAID6) and has daily rolling-over snapshots. We are in the process of extending storage in form of a archive storage which will be accessible in the near future. 

Research groups can have access to two types of storage: Hot and Cold

- **Hot data** is data that is currently in use, accessed or extended frequently. This type of storage is ideal for experimental results, manuscripts in progress etc.
- **Cold data** is data that is solely for archive. Technically, our storage is *Warm* as the data can be read at anytime, albeit not modified. The storage is a so called WORM (Write Once Read Many), where after a grace period (4 days in our case), the data is then immutable *ad vitam eternam*. This type of archive is perfectly suited for raw data.


## Accessing data on hopper 

To access your files on `hopper`, log-on to `micro` and then:

```bash
newgrp PI #first letter of PIs first name followed by their last name
srun -A PROJID -p ioa ls -l /mnt/hopper/project/PI/sequencing

# If you want to retrieve data/copy/etc., always use the same prefix but give it the -t argument (from running time, default is 15 mins, max is 2 days) :
srun -A PROJID -p ioa -t DD-HH:MM:SS <COMMAND> # COMMAND is a placeholder for the command you want to run

# And if you want an interactive session:
srun -A PROJID -p ioa -t DD-HH:MM:SS --pty bash -l

# In all of this DD-HH:MM:SS is the format, replace with days, hours, minutes and seconds. You can also simply use HH:MM:SS, e.g. 2:00:00 is two hours while 48:00:00 is two days.

# GOOD TO KNOW:
# bash is useful as most script are written in bash, but the default shell for most users on micro is `zsh` (you can check with echo $SHELL). To use the advantage of zsh in an interactive session (e.g. completion, colouring, etc.), call zsh instead as in:
srun -A PROJID -p ioa -t DD-HH:MM:SS --pty zsh -l
```

## Directory structure

While for the most part, the directory structure, besides the microscopy folder, is up to the users to decide, we highly recommend following the structure below:
    
        proj
        |- raw
        |- backup
        |- no-backup

The `raw` and `backup` directories contain your raw data and the final results. These directories will be designated for long term archive storage (COLD). The `no-backup` directory will act as a temporary directory to store all intermediary files produced as part of running any workflow. This directory should be easily purged for e.g in cases where you need to reclaim some space.   

With regards to the microscopy folder, every group that uses the microscope will have a microscopy folder in their storage directory. It is important to note that this directory is visible to all that have access to the microscope's associated computers. Do not store any sensitive data in that folder. More on that [here](Microscopy.md). 