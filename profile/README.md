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



## Acknowledgement
This research is supported by ZTE Communication Technology Service Co., Ltd., China.
