## QUAINT Network Simulator

This is the official webpage for **Quaint**: (**QU**ality-of-service-**A**ware **I**ntelligent **N**etwork digital **T**win).

**Quaint** is a highly efficient parallel and distributed simulator for QoS-aware DiffServ networks. 
**Quaint** is built on [ROSS](https://ross-org.github.io/), and utilises the _optimistic_ parallel discrete event simulation (PDES) technology to achieve fast execution.

A paper for the design and performance characterisation of **Quaint** has been submitted to [Euro-Par 2024](https://2024.euro-par.org/).

This page contains all the source code, input data and results of the paper's experiments. 
The accuracy and efficiency of **Quaint** have been evaluated against OMNeT++ with the [INET](https://inet.omnetpp.org/) model library.
In particular:
- The experiments related to **Quaint** can be found in the repo [ROSS-Network-Model](https://github.com/network-digital-twin/ROSS-Network-Model)
- The experiments related to OMNeT++/INET can be found in the repo [omnet-bench](https://github.com/network-digital-twin/omnet-bench)
- The scripts for data cleaning, visualisation, etc., are in the repo [experiment-utils](https://github.com/network-digital-twin/experiment-utils). Especially, the plotting scripts for all figures can be found in [src/plots.ipynb](https://github.com/network-digital-twin/experiment-utils/blob/experiments-metis/src/plots.ipynb) of the `experiments-metis` branch.

## Parameters used in the evaluation 

<img src="https://github.com/network-digital-twin/.github/assets/15967195/5ad458ef-6344-42f4-8560-dc2294b1bdda" alt="zte-subgraph-0" style="width:500px;"/>


### Node level configurations:
```
Propagation delay: 4ms
```
### QoS configurations:
```
One bit of the packet consumes one token.
Each packet is 1400B.

srTCM meter:
CBS = 1400*50*8;
EBS = 1400*500*8;
CIR = egress_port_bandwidth/number_of_priority_levels

Shaper:
capacity of the token bucket: 2*1400*8 tokens
token generation rate: same as the egress port bandwidth

Queue size:
priority 0: 5MB (~3571 packets)
priority 1: 20MB (~14285 packets)
priority 2: 20MB (~14285 packets)

RED dropper：
YELLOW_DROPPER_MAXTH ：capacity_of_its_attached_queue_in_bytes/1400*0.6
GREEN_DROPPER_MAXTH ：capacity_of_its_attached_queue_in_bytes/1400*0.9

```

### Distributed Execution:
All experiments in this paper were run on a cluster of four DELL PowerEdge T64 servers. Each server has 40 CPU cores (Gold 6230 2.1G*2), 256G RAM, and 1.92TB SSD. All servers are connected via 56Gbps InfiniBand FDR to a Mellanox SX6036 switch. Each server is installed with Ubuntu 20.04.6 LTS, OpenMPI 4.1.6 and UCX 1.15.0.
| No. processes | No. servers | No. processes per server |
|---------------:|-----:|-----------:|
| 1  | 1  | 1        |
| 2  | 1  | 2        |
| 4  | 1  | 4        |
| 8  | 1  | 8        |
| 16  | 1  | 16        |
| 20  | 1  | 20        |
| 29  | 2  | 14 and 15        |
| 32  | 2  | 16        |
| 56  | 4  | 14        |
| 57  | 4  | 14, 14, 14 and 15       |
| 60  | 4  | 15        |


## Acknowledgement
This research is supported by ZTE Communication Technology Service Co., Ltd., China.
