## Summary of the paper: 
Exploring Hybrid Classical-Quantum Compute Systems through Simulation

## Authors: 
Muhammad Nufail Farooqi, Martin Ruefenacht (Affiliated to: Leibniz Supercomputing Centre of the Bavarian Academy of Sciences and Humanities Garching near Munich, Germany)

## Published in: 
[2023 IEEE International Conference on Quantum Computing and Engineering (QCE)](https://ieeexplore.ieee.org/xpl/conhome/10313590/proceeding)

## Introduction:

The authors discuss various advances in the fields of science, extensive use of AI and Data Science and their interrelation with high computational facilities. They mention the increased demand for computing this brings about, for diverse industrial and academic needs. High Performance Computing (HPC), which is essentially the scaling up of compute nodes by leveraging resources owned by a user with remote resources has evolved to meet these demands. HPC’s compute power could be harnessed either through the multicore accelerators or through advances in quantum and neuromorphic computing with their special properties helping in bulk data processing and delivery efficiency. The authors highlight the potential of quantum computing to be used as an accelerator for an HPC ecosystem owing to the requirement of classical computing for operation. Specialized ways of hardware maintenance and optimization during compilation are the current limitations to quantum computing’s usage. The most appropriate utilization of quantum computing is claimed to be as a shared resource. This introduces the need for job scheduling to minimize wait times, reduce overhead and maximize efficiency. Since the domain of hybrid HPCQC (High-Performance Computing and Quantum Computing) started evolving, simulation softwares are found to be useful to explore the parameters important for integration from different stakeholder viewpoints(hardware technicians, scientists, researchers, IT industry, cloud providers, personnel of a Nation's computing missions). The authors’ work focuses on the software aspects involving various processing units , compute nodes, networks, applications and scheduling policies.

## HPCQC Integration:

This involves two steps, namely,

1. The placement of hardware components (the Processing Unit, Nodes, Networks) to establish a communication interface between the quantum and HPC systems.
2. Integration of software stacks and applications of the two systems.


Key considerations during integration are:

1. Latency
2. Fine-grained scheduling for proper resource allocation
3. Characteristics of hybrid applications in use like Variational Quantum Algorithms


Scheduling algorithms used :

1. FIFO: Similar to the operation of a queue, works in the order of entry of processes
2. Priority: Highest priority processes are executed first
3. Hybrid: Combination of the FIFO and Priority approaches.
The metric considered for the operation of HPCQC with Variational Algorithms is the ratio between the classical to quantum compute time due to a difference in the representational models. Quantum-classical interactions are unpredictable due to variation in the number of processes needing quantum nodes, and thus various degrees of communication.

Latency between Hpc and Qc depends on the number of qubits in the quantum system which determines the rate of information flow.



## Simulation Model and Implementation:

The Hybrid System Simulator consists of the hardware, software components and an optional component called the remote task execution service. The simulator is designed as a plug-and-play model to customize components as per need. Provision for using remote processing units, implementing and testing different scheduling policies is ensured with sufficient degree of interaction allowed to experiment on the system performance.

Hardware Components:

1. Processing Unit: This is an object that consists of a compute model and a task queue that has the task set given by the head/owner node. The functions are defined within the compute and task_handles methods, respectively, including the policies and signals.
2. Node: There are two types of nodes in the system, called the head and compute node. The head node keeps a track of the processes and assigns them to the available PUs using the scheduling policies. The compute node then performs the required computations to finish the job.
3. Network: Shows the connectivity of all the nodes to facilitate exchange of tasks and messages. The initial model follows a static implementation of the network latency model needed to transmit messages effectively, without a serious consideration on all network parameters.


Software Components:

1. Task: Represents a classical computation, quantum computation, data-flow or communication. Associated with an owner node and owner process.
2. Taskgraph: A model of the behavior of an application, or an intermediary representation with an acyclic graph consisting of task nodes and dependency edges. The simulator comes pre-built with common application types.
3. Process: Executing instance of the taskgraph. Associated with an identification number.
4. Job: An encapsulated representation of the task, having the type and number of compute nodes required to run, and details of interdependent processes.

## Conclusion:

The simulator serves as an important tool for experimenting on the characteristics of HPCQC system to check the efficiency in completing jobs and their dependency on network latency, coupling frequency that measures the number of different classical and quantum computation tasks, classical to quantum compute ratio, and task level scheduling policies. The experiments can be currently done with mid-size quantum systems. Improvements in quantum systems and optimizations in scheduling algorithms and compilation could be added to the simulator to help in the standardization of integration of HPC and QC.

## Applications Identified:

1. Nanobiotechnology simulations: These often require HPC systems due to the introduction of dynamic force fields that can be integrated with physics-informed computing for all atom simulations. The number of atoms can range in millions and the approximation algorithms used are in the scale of O(N log N) or O(N^2). A HPCQC system can significantly help reduce this complexity and enable relatively easier access through the cloud for a larger user-base than what is possible for the present supercomputing systems.
2. Quantum communication systems, Simulating cognitive radios for space applications
3. Climate and weather monitoring on Earth and distant planets (Further Reference: [https://www.nasa.gov/general/five-ways-nasa-supercomputing-takes-missions-from-concept-to-reality/](https://www.nasa.gov/general/five-ways-nasa-supercomputing-takes-missions-from-concept-to-reality/)
4. Algorithmic trading (Further Reading- Algorithmic Trading HPC and AI Reference Guide:[https://www.delltechnologies.com/asset/en-us/products/ready-solutions/industry-market/hpc-ai-algorithmic-trading-guide.pdf](https://www.delltechnologies.com/asset/en-us/products/ready-solutions/industry-market/hpc-ai-algorithmic-trading-guide.pdf) by Dell)

   
## Happy Discovering!!!

References:

M. N. Farooqi and M. Ruefenacht, "Exploring Hybrid Classical-Quantum Compute Systems through Simulation," 2023 IEEE International Conference on Quantum Computing and Engineering (QCE), Bellevue, WA, USA, 2023, pp. 127-133, doi: 10.1109/QCE57702.2023.10196.
