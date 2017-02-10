[pankajnetweb@c08m ~]$ cat pbstest.sh
#/bin/bash -l
#PBS -N test_job
#PBS -l nodes=2:ppn=1
#PBS -o  out-test.log
#PBS -e Error.log
cat $PBS_NODEFILE>nodes
module load mpi/openmpi/x86_64
mpirun -machinefile ./nodes np 2 ./cpi
hostname
[pankajnetweb@c08m ~]$
