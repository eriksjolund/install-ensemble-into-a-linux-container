# install-ensemble-into-a-linux-container
Install Ensemble Suite (NMR software) into a Linux container.

## Introduction

Writing down some notes about attempts to install Ensemble into a Singularity Linux container.
The Ensemble software is avaible from:
http://abragam.med.utoronto.ca/~JFKlab/

## Building the Singularity container

Singularity version 3.0.1 was used

```
    user@laptop:~$ singularity --version
    singularity version 3.0.1-145.gc9822fec
```


Clone the repo 

```
    user@laptop:~$ git clone https://github.com/eriksjolund/install-ensemble-into-a-linux-container.git 
```

Build the container

```
    user@laptop:~$ sudo singularity build install-ensemble-into-a-linux-container/ensemble.dif
```
