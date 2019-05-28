# Introduction/ Basics

## Vocabulary
- High performance computing: practice of aggregating computing power in a way that delivers much higher performance than one could get out of a typical desktop computer or workstation in order to solve large problems
- Cluster: individual computers work together to solve problem that is larger than any one computer can solve 
- Node: single computer that is part of a cluster
- Slurm: open-source system to manage the nodes and perform traffic control
- Latency: time delay between simulation and response (goal: low latency between nodes)
- Bandwidth: amount of data sent between nodes in a given amount of time (goal: high bandwidth)

## Why Use a Cluster? 
- Don't want to tie up your own machine for many hours or days 
- Have many long running job to run (most common reason)
- Parallel computing 
- Need more disk space 
- Need more memory 
- Want to use a software installed in cluster
- Want to access data stored on cluster
- Want to use GPUs (Graphic Processing Units) -> really fast for uses like deep learning

## Limitations of Clusters 
- Cannot run Windows or Mac programs -> need Linux
- Not ideal for persistent services (DBs or web servers -> you'll be in a random node so not ideal to store ) 
- Not ideal for interactive, graphical tasks
- Jobs that run for weeks can be a problem (unless checkpointed)

## Running jobs on a cluster 
### Interactice 
- request an allocation 
- system grants you one or more nodes 
- logged onto one or more nodes 
- run commands 
- exit and system automatically release nodes 

### Batch 
- write job script containing commands 
- submit the script 
- system grants you one or more nodes 
- script is automatically run on one of the nodes 
- script terminates and system relesases nodes 
- system sends notification via email 

## Interactive vs. Batch 
### Interactive 
- like a remote session 
- require an active connection -> can't shut down local computer
- for development, debugging, or interactive environments like R and Matlab 

### Batch Jobs 
- non-interactive
- can run many jobs simulatenously 
- your best choice for production computing

## Slurm -> Job scheduler 
- interactive node allocation
- Batch job submission 
- specifying and reserving resources you need for your job 
- Listing, running, and pending jobs 
- cancelling jobs 
- Grouping node resources into partitions 
- Prioritizing and scheduling jobs 

## Setting Up for Yale clusters
- request an account through [Account Request](https://research.computing.yale.edu/support/hpc/account-request)
- Submit your SSH key -> follow the instructions here [Quick Start](http://docs.ycrc.yale.edu/clusters-at-yale/access/)
- then SSH into the cluster

## Useful Commands
### srun 
- srun -h -> see all the possible flags with srun command 
- srun --pty <program name> -> run the program (most of the time, you will use bash which is the shell)
- srun --pty -p interactive bash -> partition for allocation or else you run into error (at least for Yale it does)
