This repository is to supplement the article "Minimizing the maximum flow loss in the network maintenance scheduling problem with flexible arc outages".

##### Instances  (NMData)

Since our problem MMFLPFAO is a variant of the maxTFFAO problem ([Boland2014](https://doi.org/10.1016/j.dam.2012.05.027)), the data sets of maxTFFAO can be reused to evaluate the algorithm for MMFLPFAO.

There are three datasets, each of them containing 8 networks and 10 job lists per network.
The j-th network for dataset i is described in the file

> /dataseti/dataj/Outmax_flowj.dat

The format is as follows. The rows starting with "node" give the node IDs. After a node i comes a list of arcs with rows of the form

> arc k : p c

The interpretation is that the arc with ID k goes from node i to node p and has capacity c.
The last two rows of the network file specify the source node and the target node.



The k-th joblist for network j of instance class i is /dataset_i/data_j/Jobmax_flow_k.dat_j
These files are just lists of jobs, where every job consists of each row of the form

> i a b c d

Here i is the job ID, a is the ID of the arc on which the job has to be performed, b is duration, c and d are the earliest start time and the latest start time of job i, respectively.



##### Results
