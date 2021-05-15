# Introduction

SDN for the Internet is broadly used as the reference model for SDMN design. The fundamental ideas from SDN for the Internet are decoupling the data and control planes and using logically centralized control to manage the forwarding problem in large-scale networks. SDMNs will not be a simple extension of the SDN concept for the Internet, as the radio access in mobile networks is different from the routing on the Internet. Software-defined features in SDMNs shall satisfy the specific needs of mobile networks.

The evolution of computer systems may give some tips on the design of SDMN. Nowadays, computer systems have advanced to such a level that the performance of a smartphone easily surpasses that of the supercomputer decades ago. This evolution is firmly backed by advances in developing the operation system (OS) and programming languages. The OS successfully decouples high-layer programs from low-layer hardware implementation.

The function abstraction and modular design of the computer system and the paradigm shift toward object-oriented programming establish design principles to master the complexity in computer systems. Computer science was born to build the theoretical foundation that further guarantees the innovation and continuous evolution of computer systems.
The design of SDMNs for RANs needs to address three fundamental problems.

The first problem concerns distributed network states in HMNs, in which each network and even each base station (BS) makes its own resource allocation decision with limited state information from others. Current mobile networks have limited support for network-level coordination. Network views at the high control layer are built on the proper abstraction of lower layers through defined open control interfaces and primitives. It turns distributed control problems in mobile networks into a centralized coordination problem, allowing more fine-grained optimization.

The second problem addresses the network configuration among multiple network entities. Network configuration needs to be done among coupled network entities by control algorithms based on the logical centralized control framework.

The third problem addresses fine-grained cooperation among different entities in the network. This kind of cooperation is mainly addressed by a self-organizing network (SON) features implemented by a bottom-up approach targeting the specific problem. As fine-grained cooperation becomes a common feature in mobile networks, a top-down approach is needed to incorporate the cooperation in the native system design.

Open control interfaces, programmable SON features, and proper network abstraction should be defined to implement and control different kinds of network cooperation in a software manner. It will provide flexibility and reduce the cost of implementing new network features in mobile networks.

# Key Enablers
* **SDN**:
The success of SDN comes from the systematic abstraction of complex networking problems on the Internet, which turns previous distributed networking problems into a logical centralized problem, where the rich theories and optimization tools well developed by computer science can be applied.
The separation of data and control planes, open control interfaces for network devices of different vendors, and programmable control make a disruptive paradigm shift in the networking business. The same level of complexity exists in HMNs but has not been systematically studied. SDN gives rise to fundamental new thinking on the design of mobile networks. The key question is how to extract the simplicity from complex radio access problems and build principles to guide the mobile network design.

* **NFV**:
NFV is an initiative from the telecom industry to achieve a more flexible and cost-efficient network architecture. The key idea of NFV is to virtualize network functions and implement them in industry standard high volume servers instead of proprietary hardware.
A virtualized network function (VNF) can be run across different software and processes through virtualization techniques. The focus of NFV is currently on infrastructure networks. It will be an essential technology to redesign the cellular CN. The combination of NFV and SDN brings new architecture design to mobile networks.

* **Cloud and Fog Computing**:
The development of SDN is tightly connected to cloud computing since cloud computing makes large-scale logical centralized control solutions feasible. Cloud computing is one enabler of NFV, too. The resource-sharing nature of cloud computing is suitable for joint signal processing and control among RANs. 
However, the traditional cloud computing architecture may hardly meet the strict latency requirements for fine timescale control functions in SDMNs. It is reasonable to move the logically centralized control close to the edge in mobile networks. Fog computing could fill this gap for better architecture design of SDMNs. Fog computing is a variant of the cloud computing concept that uses the computer resources and storage at the edge of a network for a substantial amount of communication, storage, control, and configuration.
In mobile networks, fog computing can be utilized for the control and joint signal processing at the RAN level to serve densely deployed cells, while cloud computing can be used for control in CNs for packet processing and forwarding. The integration of fog computing and cloud computing may lead to an end-to-end (E2E) SDN solution for mobile networks.

# SDMN Implementation
The following figure illustrates the central elements of SDMN. The key enablers in the architecture consist of the MobileFlow forwarding engine (MFFE) and MobileFlow controller (MFC).

![Picture1](https://user-images.githubusercontent.com/66460485/118368135-c3e25f00-b5b6-11eb-8697-c4b094f46eee.png)

Here there is a split that decouples mobile network control from all user plane elements. This way, the (new) user plane (i.e., the MFFE) becomes simple, stable, and high-performing, while the control plane (i.e., the MFC and mobile network applications) can be implemented in a logically centralized manner.

Forwarding in the MFFE can be fully defined in software, while the control software can flexibly steer user traffic to different service enablers that can be distributed throughout the mobile network. This design facilitates swift network innovation through network function virtualization.

In the control plane, the mobile network applications running on top of an MFC can function as an MME or the gateway control part of a physical box (indicated as GW-C), and thus can easily interact with legacy EPC network elements. 
