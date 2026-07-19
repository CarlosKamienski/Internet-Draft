---

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


# Challenges in Smart Application Development and Deployment

The IoT computing continuum introduces challenges that fundamentally affect both the development and deployment of smart applications. Unlike centralized environments, where development and deployment can often be treated as loosely coupled phases, the heterogeneity, distribution, and dynamism of the continuum create strong interdependencies between application design choices, deployment decisions, and runtime behavior. As a consequence, development and deployment concerns cannot be effectively addressed in isolation.

A primary challenge stems from the bidirectional influence between application development and deployment constraints. Decisions made during development, such as functional decomposition, communication patterns, and state management, directly impact deployment feasibility across constrained devices, edge nodes, and cloud platforms.

At the same time, deployment realities related to resource availability, network conditions, latency requirements, and energy constraints frequently impose limitations that shape or even redefine application design. This mutual influence complicates traditional workflows that assume stable execution environments and late-stage deployment decisions.

Heterogeneity across the continuum further amplifies this challenge. Execution environments differ widely in terms of hardware capabilities, operating systems, runtime support, and management interfaces. Developers must therefore anticipate deployment diversity early in the development process, while deployment mechanisms must accommodate application abstractions that span multiple platforms.

Without integrated development and deployment considerations, solutions tend to become brittle, tightly coupled to specific environments, and difficult to evolve.

Another challenge arises from the dynamic nature of deployment in the IoT computing continuum. Smart applications often need to adapt to changing conditions, such as workload variations, mobility, intermittent connectivity, or evolving physical contexts. Supporting such adaptation requires continuous feedback between runtime behavior and development-time assumptions.

Static deployment models and rigid application designs limit the ability to respond to these dynamics, underscoring the need for approaches that treat deployment as an ongoing process rather than a one-time event.

These challenges align with principles commonly associated with DevOps practices, which emphasize continuous integration, continuous deployment, and feedback loops between development and operations. However, transferring DevOps concepts to the IoT computing continuum is non-trivial. Conventional DevOps pipelines are typically designed for cloud-centric environments and assume homogeneous infrastructure, reliable connectivity, and centralized control.

In contrast, IoT scenarios involve constrained devices, distributed execution across multiple continuum stages, and, in many cases, multiple administrative domains, which complicates the application of traditional DevOps assumptions.

Finally, the absence of shared abstractions and terminology for reasoning about development and deployment in the continuum makes it difficult to compare approaches and to identify common requirements. When the interplay between development and deployment is not made explicit, solutions often remain ad hoc and platform-specific.

Addressing this gap requires an application-centric perspective that explicitly acknowledges development--deployment interdependencies and treats them as first-class concerns. Such a perspective is essential for advancing research on smart application deployment and for informing future standardization efforts related to the IoT computing continuum.

# Conceptual Deployment Model

This section outlines a conceptual model for reasoning about the deployment of smart applications across the IoT computing continuum. The model is intended to support analysis and discussion rather than to prescribe specific mechanisms, architectures, or workflows. Its purpose is to provide a shared abstraction that captures how application structure, execution environments, and coordination mechanisms interact in heterogeneous and dynamic IoT scenarios.

At the core of the model is the separation between application logic and execution environments. Application logic is represented independently of where it executes, allowing functionality, dependencies, and interaction patterns to be reasoned about without binding components to specific devices or platforms. Execution environments are treated as abstract resources characterized by capabilities, constraints, and operational context, such as computational power, connectivity, proximity to data sources, and energy availability.

Within this model, a smart application is viewed as a set of functional components connected through data and control dependencies, forming a logical application graph. Deployment consists of mapping these components onto available execution environments across the IoT computing continuum. This mapping determines where components execute, but it does not, by itself, define how they coordinate during execution. As a result, deployment decisions must be considered together with coordination strategies that govern interactions among distributed components.

Coordination among application components can be conceptualized using different styles, most notably orchestration and choreography. In an orchestration style, coordination is driven by explicit control logic that manages execution order, data flow, and component interactions. This style provides a global view of application behavior and can simplify reasoning about end-to-end execution, but it may introduce centralization and scalability concerns in highly distributed environments. In contrast, a choreography style relies on local interactions and shared interaction rules, allowing components to coordinate in a decentralized manner without a single point of control. This style can improve scalability and resilience, but it may complicate global reasoning and debugging.

The choice between orchestration and choreography, or combinations thereof, is closely tied to deployment decisions and to the characteristics of the IoT computing continuum. Resource constraints, network conditions, mobility, and administrative boundaries may favor one coordination style over another at different stages of the continuum. Moreover, coordination strategies may need to evolve over time as applications adapt to changing conditions, reinforcing the dynamic nature of deployment.

The conceptual deployment model, therefore, treats placement, coordination, and lifecycle management as interrelated concerns. Beyond initial placement, deployment encompasses actions such as reconfiguration, scaling, migration, and adaptation of coordination strategies. Runtime observations, including performance metrics and failure events, provide feedback that can inform both deployment decisions and future iterations of application design. By explicitly incorporating coordination styles into the deployment model, this abstraction provides a more concrete foundation for discussing development--deployment interdependencies in the IoT computing continuum, while remaining agnostic to specific technologies or implementations.

# Illustrative Scenarios

We present two illustrative scenarios that ground the conceptual deployment model discussed earlier. The scenarios are intended solely to demonstrate how application-centric concepts, deployment decisions, and coordination styles manifest in realistic settings, without prescribing specific technologies or architectures. The first scenario describes a smart irrigation application deployed in operational agricultural settings, providing a concrete reference for placement and lifecycle concerns under real-world constraints. The second scenario describes a drone-based delivery application that spans a broader range of continuum stages and exhibits a richer interplay between coordination styles.


## Smart Irrigation in Precision Agriculture

Smart irrigation applications collect environmental data, such as soil moisture and weather conditions, and use it to determine how much, when, and where to irrigate. In operational deployments, these applications typically span constrained sensor devices in the field, low-power gateways acting as radio concentrators, on-premises edge nodes located in farm facilities, and cloud services used for analytics, forecasting, and long-term storage. End users interact with the application through mobile or web interfaces to inspect data and approve irrigation plans.

From an application-centric perspective, the irrigation scenario exemplifies how functional decomposition maps naturally onto multiple continuum stages. Sensing and local preprocessing functions execute on constrained devices and field gateways. Intermediate functions, such as data filtering, sensor calibration, and resilience against disconnections, execute on on-premises edge nodes, which are positioned close to the irrigation infrastructure and remain operational even when connectivity to the cloud is unavailable. More computationally intensive functions, including data fusion, soil moisture forecasting, and irrigation optimization, run on cloud platforms that offer greater resources and broader data visibility.

A defining property of this scenario is the need to continue operating under intermittent wide-area connectivity, a common condition in rural deployments. Functions placed at on-premises edge nodes are expected to sustain essential behavior when cloud services are temporarily unreachable, such as enforcing safety thresholds or executing simplified local models, and to reconcile state once connectivity is restored. This requirement directly influences how application functions are decomposed at development time and where they are deployed, illustrating the bidirectional influence between development and deployment concerns discussed in earlier sections.

The irrigation scenario also highlights that deployment decisions extend beyond initial placement. Over time, functions may be updated, reconfigured, or extended to incorporate new models or new sensor modalities, and the same application logic may need to be deployed across multiple farms with different infrastructure configurations. These lifecycle aspects underscore the relevance of an application-centric view that treats deployment as an ongoing process rather than a one-time event.

## Drone-Based Delivery in Urban Environments

A drone-based delivery application uses unmanned aerial vehicles to deliver packages in urban areas. The application comprises multiple functional components, including mission planning, navigation, sensing, local coordination, and backend services for order management and analytics. From an application-centric perspective, these components form a logical application graph, with dependencies reflecting data flows and control interactions among functions. The application operates across the full span of the IoT computing continuum, leveraging constrained onboard devices, nearby edge nodes, operator-provided cloudlets, and cloud platforms.

Low-level sensing, actuation, and real-time navigation functions execute directly on the drone due to strict latency and control requirements. Local coordination and situational awareness functions may execute on nearby edge nodes or gateways that aggregate information from multiple drones operating in the same area. Operator-provided cloudlets, for example, those associated with 5G or future 6G infrastructure, can host functions that support cooperative behavior among drones, such as collision avoidance assistance and shared situational awareness. Backend services, including mission planning, optimization, logging, and analytics, typically run on cloud platforms that provide greater computational resources and global system visibility.

This scenario is particularly relevant for illustrating the coexistence of different coordination styles within a single application. Mission planning and high-level task assignment naturally follow an orchestration style, in which a centralized component coordinates delivery schedules and routes based on global system state. In contrast, local interactions among drones, such as collision avoidance or cooperative sensing, follow a choreography style, relying on decentralized interactions and shared interaction rules without a single controlling entity. Both coordination styles coexist within the same application and are influenced by deployment choices across the continuum, demonstrating that the distinction between orchestration and choreography is not merely theoretical but reflects concrete architectural trade-offs.

Deployment decisions in this scenario are also inherently dynamic. As drones move through different environments or experience changing network conditions, mappings of coordination functions to edge nodes or cloudlets may need to be revised, while backend services remain centralized. The application lifecycle extends beyond initial deployment, with components being updated, reconfigured, or migrated in response to changes in delivery demand, failures of individual drones, or variations in network availability.

## Discussion

Together, these two scenarios illustrate the spectrum of smart applications that operate over the IoT computing continuum. The first grounds the discussion in operational deployments with documented constraints, particularly around intermittent connectivity and the need for resilient edge behavior. The second reveals the broader architectural space where placement, coordination, and lifecycle concerns fully manifest, including the explicit coexistence of orchestration and choreography within a single application. Both share the fundamental property that application behavior emerges from the coordinated execution of distributed functions across heterogeneous stages, reinforcing the need for application-centric perspectives on deployment and lifecycle management.

# The Role of AI Agents in Application Deployment

The conceptual deployment model discussed earlier treats placement, coordination, and lifecycle management as interrelated and inherently dynamic concerns. As the scale, heterogeneity, and dynamism of the IoT computing continuum increase, capturing these concerns through static policies or manual procedures becomes progressively less tractable, particularly when application workloads exhibit heterogeneous, context-sensitive behavior. AI agents, understood here as autonomous software entities capable of perceiving their environment, reasoning about goals, and acting upon deployment infrastructure, offer a promising approach to managing this complexity. Foundational work on multi-agent systems [WOOLDRIDGE-AGENTS] provides established abstractions for reasoning about agent behavior. This section examines the role of such agents from an application-centric perspective, without prescribing specific agent architectures, frameworks, or protocols.

AI agents relate to application deployment in two complementary ways. First, agents can act as enablers of the deployment process itself, assisting in or automating decisions about the placement, coordination, adaptation, and lifecycle management of application functions. Second, agents are themselves software components that must execute somewhere in the continuum; consequently, the deployment of agents becomes a concern in its own right, subject to the same placement considerations that apply to application functions. These two roles are examined in turn.

## Agents as Enablers of the Deployment Process

In their first role, AI agents support the deployment of the services that compose a smart application across the IoT computing continuum. Given a logical application graph and a set of available execution environments, agents can evaluate candidate mappings of functions to continuum stages, taking into account application-level requirements such as latency, resilience, energy consumption, and data locality, as well as runtime observations of infrastructure conditions. Beyond initial placement, agents can drive lifecycle operations, including reconfiguration, scaling, migration, and partial redeployment, in response to workload variations, mobility, connectivity disruptions, or evolving physical contexts.

A concrete example arises in the deployment of inference workloads based on large language models, where placement decisions must balance latency, cost, and resilience to connectivity disruptions. Preliminary work by the authors suggests that adaptive placement strategies driven by agents can outperform static configurations, particularly under variable demand or intermittent wide-area connectivity.

Agent-assisted deployment does not presuppose a particular coordination style. A single agent with global visibility may coordinate deployment decisions in an orchestration style, while multiple agents interacting through shared rules may realize deployment coordination in a choreography style. Recent proposals illustrate early attempts to standardize agent interaction semantics along these two styles: the Model Context Protocol [MCP] emphasizes orchestration-style interactions between an agent and the tools or services it invokes, while agent-to-agent interaction frameworks [A2A] emphasize choreography-style interactions among peer agents coordinating without a central controller. In practice, agents distributed across the continuum communicate with one another at all stages to coordinate the deployment process, exchanging information about local resource availability, observed conditions, and pending deployment actions. This inter-agent communication allows deployment decisions to reflect both local knowledge, available only close to constrained devices, and global objectives, maintained at cloud platforms, and suggests that hybrid combinations of orchestration and choreography may emerge naturally in agent-based deployment.

## Deployment of the Agents Themselves

In their second role, agents appear as deployable entities. Because agents are software components, they require execution environments with sufficient computational, memory, and connectivity resources. In principle, agents can execute at any stage of the IoT computing continuum, from gateways and edge nodes to cloudlets and cloud platforms, with the choice of stage influencing the timeliness of their decisions, their visibility into local conditions, and their resilience to connectivity disruptions.

Constrained devices deserve particular attention in this respect. Many such devices lack the resources to host a full agent runtime, yet deployment decisions may still need to account for, and act upon, conditions observed at the device level. A proxy-based approach can address this asymmetry: a lightweight proxy executing on the constrained device represents it toward an agent running at a nearby stage, such as a gateway or an edge node, which performs reasoning on the device's behalf. This pattern preserves the reach of agent-based deployment down to the most constrained stages of the continuum while respecting the resource limitations discussed in [I-D.ietf-iotops-7228bis].

The deployment of agents thus exhibits a recursive character: the mechanisms that agents provide for deploying application functions apply, in principle, to the agents themselves. Placement, migration, and lifecycle management of agents raise questions similar to those discussed for application components, compounded by additional concerns regarding trust, accountability, and control when agents operate autonomously across administrative domains. Open research questions arising from this dual role are outlined in the Research Directions section.


# Relationship to Ongoing Research and Standardization

The issues discussed in this document build on existing research and standardization efforts related to edge computing and the computing continuum, including work within the IETF and IRTF, such as [RFC9556], as well as broader academic perspectives, such as [CONTINUUM-SURVEY]. Within the IRTF, the T2TRG has explored programmability, coordination, and interoperability among connected devices.

Several concrete research efforts have examined application-centric aspects of the IoT computing continuum and informed the perspective adopted in this document. Work on the notion of an IoT computing continuum as a unifying framework for reasoning about development and deployment choices has clarified the role of distributed application stages [IOTINUUM]. Complementary work on deployment-aware approaches, such as IoTDeploy, has explored how application components can be systematically placed and migrated across continuum stages while preserving application-level properties [IOTDEPLOY]. More recent efforts have investigated integrated frameworks for developing and deploying continuum-aware smart applications, providing concrete examples of how application-centric abstractions can be realized in practice. These efforts are cited here as representative examples of ongoing work in the area and not as prescriptive references; this document remains agnostic to specific frameworks or implementations.

Community-driven efforts, including workshops focused on future Internet research, have also discussed application deployment over the IoT computing continuum in the context of IETF and IRTF engagement, as exemplified by [WPIETF2025]. This document complements these efforts by adopting an application-centric perspective on deployment and lifecycle management.

# Research Directions

The challenges and conceptual considerations discussed in this document point to several open research directions for smart application development and deployment across the IoT computing continuum. These directions are not exhaustive. Rather, they highlight areas that require further investigation to better understand the interplay among application structure, deployment decisions, coordination strategies, and lifecycle management in heterogeneous and dynamic environments.

A first research direction concerns the definition of application-centric abstractions for deployment. While existing work has extensively explored infrastructure-level aspects of edge and continuum computing, there is a clear need for abstractions that allow applications to express functional decomposition, dependencies, and non-functional requirements independently of specific execution environments. Such abstractions would enable more systematic reasoning about placement, migration, and adaptation of application components across different stages of the IoT computing continuum, complementing existing architectural perspectives on edge computing [RFC9556] and broader analyses of the computing continuum [CONTINUUM-SURVEY].

A second research direction involves integrated approaches to application development and deployment. In the IoT computing continuum, development-time decisions about application structure, communication patterns, and state management are tightly coupled with deployment constraints, such as resource availability, connectivity, and latency. Traditional workflows that treat development and deployment as largely independent phases are therefore insufficient. Further research is needed to explore models, methodologies, and tools that explicitly account for this interdependence and that support feedback loops between design-time assumptions and runtime observations, building on early deployment-aware approaches such as those discussed in [IOTDEPLOY].

Coordination strategies for distributed applications constitute another important research direction. Orchestration and choreography are complementary styles for coordinating distributed application components, each with distinct trade-offs in scalability, resilience, observability, and manageability. Understanding how these coordination styles can be combined, adapted, or dynamically transitioned as applications evolve and deployment conditions change remains an open problem. This includes investigating how coordination strategies interact with placement decisions, fault handling, and lifecycle operations across heterogeneous execution environments in the IoT computing continuum.

Automation and intelligence in deployment and lifecycle management represent a further area for research. Given the scale, heterogeneity, and dynamism of IoT environments, manual deployment, configuration, and adaptation quickly become impractical. Research into automated, declarative, or policy-driven approaches for placement, migration, and reconfiguration may help address these challenges, provided that such approaches remain transparent, controllable, and aligned with application-level objectives. These mechanisms must also account for IoT-specific constraints, including limited resources, intermittent connectivity, and decentralized control across administrative domains.

An additional research direction builds on the dual role of AI agents in deployment discussed earlier in this document. That discussion raises open questions that remain largely unresolved: how agent responsibilities should be distributed between application-level and infrastructure-level concerns; how inter-agent interactions can be made secure, auditable, and aligned with Internet architectural principles, particularly when agents interact across administrative domains and heterogeneous environments; how orchestration and choreography styles may be combined dynamically in agent-based deployment; and how the placement and lifecycle of the agents themselves, including proxy-based representation of constrained devices, can be managed without introducing new points of fragility or centralization. Emerging interaction frameworks such as [MCP] and [A2A] remain evolving, and further research is needed to assess how agent-based mechanisms can complement application-centric deployment models in the IoT computing continuum.

Finally, there is a broader need for shared terminology and conceptual frameworks that facilitate comparison across research efforts and support dialogue with standardization activities. Without a common vocabulary for reasoning about application-centric deployment and lifecycle management in the IoT computing continuum, research results risk remaining fragmented and difficult to generalize.

Informational documents that clarify the problem space, such as this one, can help align research agendas and identify areas where future standardization efforts within the IRTF or the IETF may be beneficial.


# Security Considerations

This document does not specify protocols, mechanisms, or architectures and therefore does not introduce new security vulnerabilities directly. However, the concepts discussed have important security implications that merit consideration.

In the IoT computing continuum, application components are distributed across heterogeneous and potentially untrusted execution environments, increasing the attack surface and complicating traditional security assumptions. Deployment decisions influence trust boundaries, data exposure, and the ability to isolate faults or compromised components.

Coordination strategies also have security implications. Orchestration-based approaches may introduce centralized control points that become attractive attack targets, while choreography-based approaches rely on decentralized interactions that require robust authentication, authorization, and trust management among components.

The tight coupling between development and deployment further emphasizes the need to consider security throughout the application lifecycle. Design-time assumptions about trust, isolation, and access control may be invalidated by deployment changes, migration of components, or dynamic adaptation at runtime. As a result, security considerations must be revisited whenever application structure, placement, or coordination strategies evolve.

Finally, the distributed and multi-domain nature of the IoT computing continuum raises challenges related to identity management, secure communication, and policy enforcement across administrative boundaries. While addressing these challenges is outside the scope of this document, they underscore the importance of integrating security considerations into research and standardization efforts related to application-centric deployment and lifecycle management.


# IANA Considerations

This document has no IANA actions.


# Acknowledgments

The authors would like to acknowledge CGI.br (Brazilian Internet Steering Committee) for its support through the IETF/IRTF participation program, which enabled engagement in research and discussions within the Internet Research Task Force (IRTF).

# Informative References

# References

**[A2A]** A2A Project, "Agent2Agent (A2A) Protocol", 2024, <https://a2aproject.github.io/A2A/>.

**[CONTINUUM-SURVEY]** Bittencourt, L. F., Rodrigues-Filho, R., Spillner, J., Turck, F. D., Santos, J., Fonseca, N. L. S. da, Rana, O., Parashar, M., and I. Foster, "The Computing Continuum: Past, Present, and Future", *Computer Science Review*, Elsevier, Vol. 58, Article 100782, DOI 10.1016/j.cosrev.2025.100782, 2025, <https://doi.org/10.1016/j.cosrev.2025.100782>.

**[I-D.ietf-iotops-7228bis]** Bormann, C., Ersue, M., Keränen, A., and C. Gomez, "Terminology for Constrained-Node Networks", Work in Progress, Internet-Draft, draft-ietf-iotops-7228bis-07, 23 April 2026, <https://datatracker.ietf.org/doc/html/draft-ietf-iotops-7228bis-07>.

**[IOTDEPLOY]** Oliveira, F. B., Felice, M. D., and C. Kamienski, "IoTDeploy: Deployment of IoT Smart Applications over the Computing Continuum", *Internet of Things*, Elsevier, Vol. 28, Article 101348, DOI 10.1016/j.iot.2024.101348, 2024, <https://doi.org/10.1016/j.iot.2024.101348>.

**[IOTINUUM]** Kamienski, C., Zyrianoff, I., Bittencourt, L. F., and M. D. Felice, "IoTinuum: The IoT Computing Continuum", *Proceedings of the 20th International Conference on Distributed Computing in Smart Systems and the Internet of Things (DCOSS-IoT)*, IEEE, pp. 732-739, DOI 10.1109/DCOSS-IoT61029.2024.00114, 2024, <https://doi.org/10.1109/DCOSS-IoT61029.2024.00114>.

**[MCP]** Anthropic, "Model Context Protocol Specification", 2024, <https://modelcontextprotocol.io/>.

**[RFC7452]** Tschofenig, H., Arkko, J., Thaler, D., and D. McPherson, "Architectural Considerations in Smart Object Networking", RFC 7452, DOI 10.17487/RFC7452, March 2015, <https://www.rfc-editor.org/rfc/rfc7452>.

**[RFC9556]** Hong, J., Hong, Y., de Foy, X., Kovatsch, M., Schooler, E., and D. Kutscher, "Internet of Things (IoT) Edge Challenges and Functions", RFC 9556, DOI 10.17487/RFC9556, April 2024, <https://www.rfc-editor.org/rfc/rfc9556>.

**[WOOLDRIDGE-AGENTS]** Wooldridge, M., *An Introduction to MultiAgent Systems*, 2nd Edition, John Wiley and Sons, 2009.

**[WPIETF2025]** Kamienski, C. A. and M. A. B. Santos, "Smart Application Deployment over the IoT Computing Continuum", *Workshop de Pesquisa em Internet do Futuro (WPIETF)*, Sociedade Brasileira de Computacao (SBC), 2025. Available via SBC Open Library (SOL).
