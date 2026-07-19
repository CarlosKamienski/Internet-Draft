---
###
# Internet-Draft Markdown Template
#
# Rename this file from draft-todo-yourname-protocol.md to get started.
# Draft name format is "draft-<yourname>-<workgroup>-<name>.md".
#
# For initial setup, you only need to edit the first block of fields.
# Only "title" needs to be changed; delete "abbrev" if your title is short.
# Any other content can be edited, but be careful not to introduce errors.
# Some fields will be set automatically during setup if they are unchanged.
#
# Don't include "-00" or "-latest" in the filename.
# Labels in the form draft-<yourname>-<workgroup>-<name>-latest are used by
# the tools to refer to the current version; see "docname" for example.
#
# This template uses kramdown-rfc: https://github.com/cabo/kramdown-rfc
# You can replace the entire file if you prefer a different format.
# Change the file extension to match the format (.xml for XML, etc...)
#
###
title: "Application-Centric Considerations for Deployment over the IoT Computing Continuum"
abbrev: "IoTinummDeploy"
category: info

docname: draft-kamienski-iot-deployment
submissiontype: IRTF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
consensus: true
v: 3
area: AREA
workgroup: RG Research Group
keyword:
 - Internet of Things (IoT)
 - Computing Continuum
 - Service Deployment
venue:
  group: RG
  type: Research Group
  mail: WG@example.com
  arch: https://example.com/WG
  github: USER/REPO
  latest: https://example.com/LATEST

author:
 -
    fullname: Carlos Alberto Kamienski
    organization: Federal University of ABC (UFABC)
    email: carlos.kamienski@ufabc.edu.br
 -
    fullname: Marco Santos
    organization: Federal Institute of Sertão (IFSertão)
    email: marcelo.santos@ifsertao-pe.edu.br

 -
    fullname: Marco Di Felice
    organization: University of Bologna
    email: marco.difelice3@unibo.it


normative:

informative:

...

--- abstract

Smart applications increasingly depend on the Internet of Things (IoT) and on distributed computing environments that span constrained devices, edge nodes, cloudlets, and cloud infrastructures, collectively referred to as the edge–cloud or computing continuum. This document uses the term IoT computing continuum to highlight the importance of IoT-specific constraints and requirements within this broader context. Although prior work has addressed communication aspects and edge functions in these environments, as noted in RFC 9556 and comprehensive surveys of the computing continuum, there has been comparatively less focus on application-centric issues such as deployment, placement, and lifecycle management. This document identifies key challenges and conceptual considerations for deploying smart applications across the IoT computing continuum, aiming to provide a unified architectural perspective and vocabulary to guide ongoing research within the IRTF and inform future standardization initiatives.

--- middle

# Introduction

The Internet of Things (IoT) has evolved from simple data collection systems into a foundation for complex, data-driven smart applications spanning domains such as smart cities, precision agriculture, industrial automation and healthcare. These applications increasingly depend on distributed computing resources to sense, process, and act on data close to where it is generated, while also leveraging large-scale cloud infrastructures for coordination, analytics, and long-term storage.

This evolution has led to the emergence of a distributed computing environment spanning multiple layers, from highly constrained devices and gateways to edge nodes, cloudlets, and centralized cloud platforms. In the literature, this environment is commonly described as the edge-cloud continuum, IoT-edge-cloud continuum, or simply computing continuum. Comprehensive perspectives on the evolution of this paradigm are provided in [CONTINUUM-SURVEY]. In this document, the term IoT computing continuum emphasizes the presence of constrained IoT devices and the domain-specific requirements they introduce.

Recent research and standardization efforts have highlighted the importance of this continuum and discussed challenges related to edge functions, data handling, and communication across heterogeneous environments, including work within the IETF and IRTF, such as [RFC9556]. However, much of the existing discussion remains infrastructure- or communication-centric, with comparatively less focus on the implications for smart application deployment and lifecycle management.

From an application perspective, smart services are no longer confined to a single execution environment. Instead, they are composed of multiple functions that must be placed, coordinated, and potentially migrated across different stages of the IoT computing continuum to satisfy requirements for latency, resilience, scalability, privacy, and energy efficiency. In practice, these decisions are often handled manually or through ad hoc mechanisms, leading to fragmented solutions and limited portability across deployments.

The lack of a shared, application-centric view of deployment over the IoT computing continuum creates challenges for both researchers and practitioners. It complicates systematic reasoning about application structure, hinders the comparison of alternative approaches, and makes it difficult to identify common requirements that could inform future research and standardization activities.

This document aims to contribute to this discussion by examining smart application deployment over the IoT computing continuum from a conceptual and architectural perspective. Rather than proposing specific mechanisms or protocols, it focuses on identifying key challenges, clarifying terminology, and outlining considerations relevant to ongoing research within the Thing-to-Thing Research Group (T2TRG) of the Internet Research Task Force (IRTF).

# Scope and Non-Goals

This document focuses on conceptual and architectural considerations for deploying smart applications across the IoT computing continuum. Its scope is limited to discussing challenges, common patterns, and terminology arising from distributed application logic across heterogeneous computing environments, including constrained IoT devices, edge nodes, and cloud platforms. The intent is to support research-oriented discussion and to provide a shared frame of reference for ongoing and future work within the IRTF. The discussion explicitly considers the interplay between application development and deployment, while remaining agnostic to specific tools, workflows, or operational practices.

The document does not specify concrete deployment mechanisms, protocols, or interfaces. It does not define a reference architecture, nor does it mandate how applications should be structured, deployed, or managed in practice. Instead, it aims to describe the problem space and highlight issues relevant across multiple technologies, deployment models, and research efforts.

In particular, the following items are explicitly outside the scope of this document:

   *  The specification of new communication protocols, APIs, or data
      models.

   *  The definition of normative requirements, including the use of
      requirement keywords such as MUST, SHOULD, or MAY.

   *  The standardization of specific platforms, frameworks, or
      programming models for IoT application deployment.

   *  Detailed performance evaluations or quantitative comparisons
      between alternative solutions.

By clearly delineating its scope and non-goals, this document seeks to complement existing and ongoing efforts in the computing continuum, including work on communication, edge functions, and operational aspects, while maintaining a technology-agnostic and application-centric perspective.

# Terminology

This document uses the following terms with the meanings indicated below. The definitions are intended to clarify usage in this document and are not meant to redefine existing terminology used elsewhere.

**Internet of Things (IoT):**
A system paradigm involving interconnected physical objects equipped with sensing, actuation, processing, and communication capabilities, operating under resource constraints, as discussed in [RFC7452].

**Constrained Devices:**
Devices with limited processing power, memory, energy availability, or communication capabilities. The use of the term *constrained* in this document follows the terminology defined in [I-D.ietf-iotops-7228bis].

**IoT Computing Continuum:**
A distributed computing environment spanning constrained IoT devices, edge nodes, and cloud platforms, where application components may execute at different stages depending on requirements and context. The shorthand term *IoTinuum* has been used in related work to denote this same concept [IOTINUUM]. This document uses the expanded form throughout for clarity and alignment with terminology used in related standardization efforts.

**Edge Node:**
An intermediate computing node located between constrained devices and centralized cloud infrastructures, providing computation, storage, and networking capabilities closer to data sources, as described in [RFC9556].

**Orchestration and Choreography:**
Two coordination styles for distributed applications. Orchestration refers to coordination driven by explicit control logic, while choreography relies on decentralized interactions among components without a central coordinator.

# Background: The IoT Computing Continuum

The increasing distribution of computation across networked systems has led to the emergence of what is commonly described as a computing continuum, spanning centralized cloud infrastructures, intermediate edge and fog nodes, and highly constrained end devices [CONTINUUM-SURVEY]. This paradigm reflects a shift away from strictly centralized processing models toward more distributed execution, driven by requirements related to latency, bandwidth efficiency, resilience, data locality, and regulatory constraints.

Within the context of the Internet of Things (IoT), this continuum acquires additional characteristics that distinguish it from more general edge-cloud computing environments. IoT deployments involve large numbers of heterogeneous devices with severe resource constraints, intermittent connectivity, and close interaction with the physical world through sensing and actuation [RFC7452]. As a result, computation is often pushed closer to data sources not only for performance reasons, but also to enable timely control actions, reduce energy consumption, and preserve privacy.

Recent research and standardization activities have explored different aspects of this continuum. In particular, work within the IETF and IRTF has highlighted the importance of edge computing and has discussed functional components and challenges associated with operating across distributed environments [RFC9556]. Existing documents have examined edge functions for data processing, storage, and communication, as well as the roles of gateways and intermediate nodes in bridging constrained devices to cloud services. These efforts provide an important foundation for understanding the structural and operational properties of the continuum.

The perspective taken in this document is complementary rather than competing. While [RFC9556] characterizes functional components and challenges at the infrastructure level, focusing on edge functions and the communication fabric that supports them, the present document shifts attention to the application layer that operates on top of such infrastructure. Specifically, it considers how smart applications, composed of multiple interdependent functions, are decomposed, placed, coordinated, and managed across the heterogeneous stages enabled by that infrastructure. Application-centric concerns such as functional decomposition, placement, coordination style, and lifecycle management are largely orthogonal to the infrastructure view and remain comparatively underexplored in current standardization discussions.

This document adopts the term *IoT computing continuum* to refer to this distributed execution environment, emphasizing the integration of constrained IoT devices, edge nodes, and cloud platforms into a unified computational space. Building on existing work, the focus here is on understanding how the properties of the IoT computing continuum influence application deployment, placement, and lifecycle management, rather than on defining specific technologies or architectural solutions.

# An Application-Centric View of the Continuum

Traditional IoT architectures often treat applications as tightly coupled to specific execution environments, typically assuming fixed roles for devices, gateways, and cloud services. In the context of the IoT computing continuum, this assumption no longer holds. Smart applications must be understood as distributed entities whose behavior emerges from the coordinated execution of multiple components across heterogeneous computing stages. Adopting an application-centric view is therefore essential to reason about deployment, adaptation, and lifecycle management in such environments.

## Applications as Distributed Functional Graphs

From an application-centric perspective, smart applications can be modeled as collections of interdependent functions rather than as monolithic software artifacts. These functions interact through well-defined data and control dependencies, forming a logical application graph that captures the application's structure independently of where its components execute. This representation enables reasoning about application behavior, dependencies, and composition without prematurely binding functions to specific devices or platforms.

Viewing applications as distributed functional graphs is particularly relevant in IoT environments, where different functions may have distinct requirements for latency, computational resources, sensor or actuator access, and interaction with external services. By separating the application's logical structure from its physical deployment, this model supports more flexible placement and adaptation strategies across the continuum.

## Decoupling Application Logic from Execution Environments

A key implication of the application-centric view is the need to decouple application logic from execution environments. Application functionality should be expressed in a way that is independent of specific hardware platforms, operating systems, or runtime environments. This decoupling enables portability across heterogeneous devices and supports dynamic reassignment of application components as execution conditions change.

In the IoT computing continuum, execution environments vary widely in terms of resource availability, connectivity, and operational constraints. Binding application logic too early to a particular environment limits the ability to adapt to failures, load variations, or evolving requirements. An application-centric approach instead treats execution environments as abstract resources onto which application functions can be mapped, allowing deployment decisions to be revisited over time.

## Placement and Distribution Across the Continuum

Once application logic is decoupled from execution environments, the placement of application functions becomes a first-class concern. Placement decisions determine where individual functions of an application execute within the IoT computing continuum, ranging from constrained devices and gateways to edge nodes and cloud platforms. These decisions directly affect end-to-end application properties, including latency, reliability, energy consumption, and data locality.

Importantly, placement is not a static decision. In many scenarios, application components may need to be redistributed in response to changes in workload, network conditions, or operational context. An application-centric view highlights the need to reason about placement and distribution as dynamic processes intrinsic to the operation of smart applications across the continuum.

## Application Lifecycle Beyond Initial Deployment

In centralized systems, application deployment is often treated as a one-time event followed by relatively infrequent updates. In contrast, the IoT computing continuum introduces a more complex and dynamic application lifecycle. Beyond initial deployment, applications may undergo continuous adaptation, including updates, reconfiguration, scaling, component migration, and partial redeployment across different continuum stages.

Managing this lifecycle is particularly challenging in IoT environments due to device heterogeneity, intermittent connectivity, and the coexistence of multiple administrative domains. An application-centric perspective emphasizes that lifecycle management must be considered holistically, encompassing not only software updates but also the ongoing coordination of distributed application components. Understanding these lifecycle aspects is essential for identifying common challenges and research questions related to deployment and operation in the IoT computing continuum.


# Conventions and Definitions

{::boilerplate bcp14-tagged}


# Security Considerations

TODO Security


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
