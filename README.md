This repository is to supplement the article "Minimizing the maximum flow loss in the network maintenance scheduling problem with flexible arc outages".

#### Instances  (NMData)

Since our problem MinMFLFAO is a variant of the maxTFFAO ([Boland2014](https://doi.org/10.1016/j.dam.2012.05.027))[^1], the data sets of maxTFFAO can be reused to evaluate the algorithm for the MinMFLFAO.

[^1]: Boland N,  Kalinowski T,  Waterer H, et al. Scheduling arc maintenance jobs in a network to maximize total flow over time[J]. Discrete Applied Mathematics, 2014, 163(1):34-52.

There are three datasets, each of them containing 8 networks and 10 job lists per network.
The $j$-th network for dataset $i$ is described in the file:

> /dataset$i$/data$j$/Outmax_flow$j$.dat

The format is as follows. The rows starting with "node" give the node IDs. After a node $i$ comes a list of arcs with rows of the form:

> arc $k : p\ c$

The interpretation is that the arc with ID $k$ goes from node i to node $p$ and has capacity $c$.
The last two rows of the network file specify the source node and the target node.

The $k$-th joblist for network $j$ of instance class $i$ is /dataset$i$/data$j$/Jobmax_flow_$k$.dat$j$
These files are just lists of jobs, where every job consists of each row of the form:

> $i\ a\ b\ c\ d$

Here $i$ is the job ID, $a$ is the ID of the arc on which the job has to be performed, $b$ is duration, $c$ and $d$ are the earliest start time and the latest start time of job $i$, respectively.



#### Results

Here we present the detailed results of three datasets, respectively. Among them, the $implementation$ column indicates the implementation method of the algorithm, 'full' is our BDA algorithm, 'without xxx cut' indicates that the BDA algorithm without xxx cut, 'Gurobi for Benders cuts' indicates using gurobi to solve the separation procedure. The columns $dataset, data, job$ correspond the instance of one network in a dataset. The columns $nodes, arcs, jobs$ are the number of the nodes and arcs of the network and the number of maintenance tasks in the instance. The columns $obj, bound$ are the lower bound and the upper bound, respectively. The $status$ column means the solving status, '2' is optimal, '9' is feasible, '11' is being aborted early. The columns $init\ cuts, opt\ cuts, forbidden\ cuts, goal\ cut$ are the number of initial optimality cuts, optimality cuts in separation procedure, forbidden cuts and goal cut added into MP, respectively. The columns $subTime, time$ indicate the solving time of separation procedure and the whole solution process in seconds. The last column $Nnodes$ is the number of explored nodes in the branch-and-bound tree.

