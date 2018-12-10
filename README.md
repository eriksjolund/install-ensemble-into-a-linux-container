# install-ensemble-into-a-linux-container
Install Ensemble Suite (NMR software) into a Linux container. 

__Status__: Right now all the software dependencies for the Ensemble software are installed into the container but not the Ensemble software itself. Instead  the Ensemble sofware is installed into the user's home directory. A future goal would be to install everything into the container.

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

See also [Singularity installation instructions](https://github.com/sylabs/singularity/blob/master/INSTALL.md)


Clone the repo 

```
    user@laptop:~$ git clone https://github.com/eriksjolund/install-ensemble-into-a-linux-container.git 
```

Build the container and have the result written to the file ensembleCentos6.sif  (an arbitrarily chosen filename).

```
    user@laptop:~$ sudo singularity build ensembleCentos6.sif install-ensemble-into-a-linux-container/ensemble.dif
```

Install Ensemble

```
    user@laptop:~$ singularity shell ensembleCentos6.sif
    Singularity ensembleCentos6:~/> cd ensemble 
    Singularity ensembleCentos6:~/ensemble> LC_ALL=C csh ensemble_inst.csh
```


Run Ensemble

```
    user@laptop:~$ singularity shell ensembleCentos6.sif
    Singularity ensembleCentos6:~/ensemble> source ~/.bashrc
    user@laptop:~$ LC_ALL=C ensemble /home/user/ensemble/ENSEMBLE/example/example.par
```
