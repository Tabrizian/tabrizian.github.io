---
title:  "Areas To Explore In Systems And Networking"
date: 2019-08-05
permalink: /posts/2019/08/areas-to-explore-in-systems-and-networking
tages:
  - Research
  - Computer Networking


---

Many students in undergrad think the only way to explore Computer Science in graduate 
studies is by studying Artificial Intelligence and Machine Learning. However,
there are many interseting areas to explore in Computer Science that many are not
aware of. Including myself, when I was trying to choose the topic that I want to 
work on for graduate studies, I wasn't aware of the interesting problems
that exist in the area of systems and networking.

In this article I want to point to out to three interesting areas in systems and networking.

# Making Datacenters Faster, Faster, and Faster!

Nowadays, datacenters and cloud computing are improving at an unprecedented speed. 
More and more workloads are being migrated to the cloud. Applications running
in cloud requirer tighter SLAs. This demands has led to research to improve
the aforementioned areas. The speed of switches and routers in data centers are 
being improved. New switches can forward packets at 100 Gb/s speed. On the other hand,
operating systems were designed for the era of dial up and KB/s speed. This design has
led to operating system being converted to the bottleneck for high speed networks. To improve
end-to-end performance of applications in cloud computing environments researchers have tried
different approaches:

## Creating Custom End-To-End Application Level Protocols

If you look at the papers released by popular systems venues, every year you
can find a paper about this topic. The best paper award winner of NSDI '19 (one of the
leading systems conferences) was about desigining a RPC protocol for datacenters.
If you are interested to read more about it you [see this link to the paper](https://www.usenix.org/conference/nsdi19/presentation/kalia) .

## Offloading Traffic Processing to FPGAs, GPU, and DPDK


### FPGAs
One of the ways to improve the performance of packet processing is using custom
hardware for packet processing. The first solution is using FPGAs. FPGAs are a piece of hardware that
enable dynamic reconifguration of connection between different sections of it. 
It enables usage of software to configure circuite (hardware). 

![FGPA](https://upload.wikimedia.org/wikipedia/commons/thumb/3/35/Fpga_xilinx_spartan.jpg/220px-Fpga_xilinx_spartan.jpg)

### GPUs

The other solution is using GPUs. GPUs provide an array of small CPUs. GPUs were
originally created for graphic processing. But other types of applications showed
similar attributes as graphic processing. Recently, Machine Learning and packet
procssing has been offloaded to GPUs to increase performance.

![GPU](https://images-na.ssl-images-amazon.com/images/I/61S5ttfWftL._SX425_.jpg)

### DPDK

DPDK (Data Plane Development Kit) tries to enable fast packet processing on CPUs.
Various CPU vendors such as Intel provide their own DPDK to optimize packet processing
on their own CPU architectures.

# Systems to Improve the Performance of Machine Learning 

Machine Learning generally contains various stages such as training, serving, 
and preprocessing. There are problems associated with each of these stages. For 
example, training of large DNNs can be very time-consuming and resource-hungry. We
may not be able to transfer data from to the cloud for learning because of privacy
concerns ([see federated learning](https://ai.googleblog.com/2017/04/federated-learning-collaborative.html)).

In the model serving phase we may want to serve multiple-models and enable caching,
low-latency models. These are the examples in which systems can help ML.

These are some of the interesting papers that have been published in this area:
* [Scaling Distributed Machine Learning with the Parameter Server](https://www.usenix.org/conference/osdi14/technical-sessions/presentation/li_mu)
* [Clipper: A Low-Latency Online Prediction Serving System](https://www.usenix.org/conference/nsdi17/technical-sessions/presentation/crankshaw)

# Edge Computing

With the advent of IoT devices, a new paradigm for computing is becoming more
and more popular. The idea of edge computing is to put the processing of applications
as close to the user as possible. This can be become challenging when the resources
which are close to user, have limited capacity. Using this approach, we can enable
mission critical low-latency applications.

These are some of the interesting papers in this area:
* [Distributing Deep Neural Networks with Containerized Partitions at the Edge](https://www.usenix.org/conference/hotedge19/presentation/zhou)
* [An Edge-based Framework for Cooperation in Internet of Things Applications](https://www.usenix.org/conference/hotedge19/presentation/leidall)


