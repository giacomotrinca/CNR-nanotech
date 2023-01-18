PBS Job Script Guide

PBS (Portable Batch System) is a software used to manage and schedule jobs on a cluster or supercomputer. This guide will show you how to write a job script for PBS using the new syntax.
Prerequisites

    A cluster or supercomputer with PBS installed
    An account on the cluster or supercomputer
    Basic knowledge of the command line and PBS commands

Script Structure

A PBS job script has a specific structure and contains various PBS directives and commands. A basic structure for a job script looks like this:

#!/bin/bash

#PBS Directives

#PBS -N job_name

#PBS -l nodes=1:ppn=8

#PBS -l walltime=12:00:00

#PBS -j oe

#PBS -q queue_name

# Job Commands
cd $PBS_O_WORKDIR

./my_executable

° The first line specifies the shell that will be used to interpret the script. In this example, it is bash.
° The #PBS directives specify various job properties such as the job name, number of nodes and processors
  per node, walltime, and queue name.
° The cd command changes the current working directory to the directory from which the job was submitted.
° The ./my_executable command is the command that will be executed by the job. This can be replaced with 
  any command or script that you want to run.

#PBS Directives

The following is a list of some common PBS directives and their uses:

    #PBS -N job_name: Specifies the name of the job. This name will be used to identify the job in the 
         PBS queue.
    #PBS -l nodes=1:ppn=8: Specifies the number of nodes and processors per node that the job will use. 
         In this example, the job will use 1 node with 8 processors per node.
    #PBS -l walltime=12:00:00: Specifies the maximum amount of time the job will run.
         In this example, the job will run for 12 hours.
    #PBS -j oe: Merges the standard output and standard error streams.
    #PBS -q queue_name: Specifies the queue that the job will be submitted to.

#Submitting a Job

To submit a job to PBS, use the qsub command followed by the path to the job script. For example:

qsub my_job_script.sh

This will submit the job to PBS and return the job ID. You can use the qstat command to check the status 
of your job.
