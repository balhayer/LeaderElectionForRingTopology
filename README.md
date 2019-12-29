# LeaderElectionForRingTopology
Leader Election For Ring Topology

Group Members:
Balwinder Singh Hayer & Saytu Singh

-Write a program using MPI to simulate a leader election algorithm for a ring topology
-Motivation was that we wanted to learn more about ring topology use this project to use on our resume 

At start on election round, each active process sends its ID to its neighbors on either side. 
Send its rank to its neighbors
Receive ranks from its neighbors
If the process’s rank is the lowest of the 3, then it will set itself to passive
If the process’s neighbor’s ranks is equal to its own rank, then it will break out of loop and elect itself LEADER.

How to Execute program:

mpicc -o ring ring.c 
mpirun -np 4 ./ring

MPI Command Used:-

MPI_Init()
MPI_Comm_size()
MPI_Comm_rank()
MPI_Comm_World
MPI_Send()
MPI_Recv()
MPI_Barrier()
MPI_Abort()
MPI_Finalize()

Technical Difficulties Encountered:-

We face difficulty formatting output from multiple processes
Cross-platform issues (different outcomes)

Shortcomings:-

Processes were not terminating due to using blocking communication
Solution: used non-blocking communication(MPI_Isend, MPI_Irecv)

