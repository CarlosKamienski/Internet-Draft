---

title: "Application-Centric Considerations for Deployment over the IoT Computing Continuum"
abbrev: "IoT Continuum Deployment"
category: info

docname: draft-kamienski-iot-deployment-latest
submissiontype: IRTF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
# consensus: true
v: 3
# area: AREA
# workgroup: RG Research Group
keyword:
 - Internet of Things (IoT)
 - Computing Continuum
 - Service Deployment
venue:
  group: Thing-to-Thing
  type: Research Group
  mail: t2trg@irtf.org
  arch: https://mailarchive.ietf.org/arch/browse/t2trg/
  github: "CarlosKamienski/Internet-Draft"
  latest: "https://CarlosKamienski.github.io/Internet-Draft/draft-kamienski-iot-deployment.html"

author:
 -
    fullname: Carlos Alberto Kamienski
    organization: Federal University of ABC (UFABC)
    email: carlos.kamienski@ufabc.edu.br
 -
    fullname: Marcelo Anderson Batista dos Santos
    ins: M. A. B. Santos
    organization: Federal Institute of Sertão (IFSertão)
    email: marcelo.santos@ifsertao-pe.edu.br
 -
    fullname: Marco Di Felice
    ins: M. Di Felice
    organization: University of Bologna
    email: marco.difelice3@unibo.it


normative:

informative:

  RFC7452:

  RFC9556:

  I-D.ietf-iotops-7228bis:

  RFC9019:

  RFC9176:

  RFC9315:

  RFC9880:

  RFC8693:

  RFC9200:

  RFC9334:

  RFC9943:

  I-D.ietf-core-comi:

  COINRG:
    title: "Computing in the Network Research Group Charter"
    author:
      - org: "IRTF"
    date: 2019-08-21
    seriesinfo:
      Charter: "charter-irtf-coinrg-01"
    target: "https://datatracker.ietf.org/doc/charter-irtf-coinrg/01/"

  WOT-TD:
    title: "Web of Things (WoT) Thing Description 1.1"
    author:
      - org: "W3C"
    date: 2023-12-05
    target: "https://www.w3.org/TR/2023/REC-wot-thing-description11-20231205/"

  SWAMP:
    title: "Smart Water Management Platform: IoT-Based Precision Irrigation for Agriculture"
    author:
      - name: "Carlos Kamienski"
        ins: "C. Kamienski"
      - name: "Juha-Pekka Soininen"
        ins: "J.-P. Soininen"
      - name: "Markus Taumberger"
        ins: "M. Taumberger"
      - name: "Ramide Dantas"
        ins: "R. Dantas"
      - name: "Attilio Toscano"
        ins: "A. Toscano"
      - name: "Tullio Salmon Cinotti"
        ins: "T. Salmon Cinotti"
      - name: "Rodrigo Filev Maia"
        ins: "R. Filev Maia"
      - name: "Andre Torre Neto"
        ins: "A. Torre Neto"
    date: 2019-01-11
    seriesinfo:
      Sensors: "Vol. 19, No. 2, Article 276"
      DOI: "10.3390/s19020276"
    target: "https://doi.org/10.3390/s19020276"

  DRONE-DELIVERY:
    title: "Drones in the Big City: Autonomous Collision Avoidance for Aerial Delivery Services"
    author:
      - name: "Fabiola M. C. de Oliveira"
        ins: "F. M. C. de Oliveira"
      - name: "Luiz F. Bittencourt"
        ins: "L. F. Bittencourt"
      - name: "Reinaldo A. C. Bianchi"
        ins: "R. A. C. Bianchi"
      - name: "Carlos A. Kamienski"
        ins: "C. A. Kamienski"
    date: 2024-05
    seriesinfo:
      IEEE Transactions on Intelligent Transportation Systems: "Vol. 25, No. 5, pp. 4657-4674"
      DOI: "10.1109/TITS.2023.3329029"
    target: "https://doi.org/10.1109/TITS.2023.3329029"

  AGENTPROTO:
    title: "Agent Communication Protocols Working Group Charter"
    author:
      - org: "IETF"
    date: 2026-10-08
    seriesinfo:
      Charter: "charter-ietf-agentproto-01"
    target: "https://datatracker.ietf.org/doc/charter-ietf-agentproto/01/"

  A2A:
    title: "Agent2Agent (A2A) Protocol"
    author:
      - org: "Agentic AI Foundation (AAIF)"
    date: 2026
    target: "https://aaif.io/projects/agent2agent"

  CONTINUUM-SURVEY:
    title: "The Computing Continuum: Past, Present, and Future"
    author:
      - ins: "L. F. Bittencourt"
        name: "L. F. Bittencourt"
      - ins: "R. Rodrigues-Filho"
        name: "R. Rodrigues-Filho"
      - ins: "J. Spillner"
        name: "J. Spillner"
      - ins: "F. De Turck"
        name: "F. De Turck"
      - ins: "J. Santos"
        name: "J. Santos"
      - ins: "N. L. S. da Fonseca"
        name: "N. L. S. da Fonseca"
      - ins: "O. Rana"
        name: "O. Rana"
      - ins: "M. Parashar"
        name: "M. Parashar"
      - ins: "I. Foster"
        name: "I. Foster"
    date: 2025
    seriesinfo:
      "Computer Science Review": "Vol. 58, Article 100782"
      DOI: "10.1016/j.cosrev.2025.100782"
    target: "https://doi.org/10.1016/j.cosrev.2025.100782"

  IOTDEPLOY:
    title: "IoTDeploy: Deployment of IoT Smart Applications over the Computing Continuum"
    author:
      - ins: "F. B. Oliveira"
        name: "F. B. Oliveira"
      - ins: "M. Di Felice"
        name: "M. Di Felice"
      - ins: "C. Kamienski"
        name: "C. Kamienski"
    date: 2024
    seriesinfo:
      "Internet of Things": "Vol. 28, Article 101348"
      DOI: "10.1016/j.iot.2024.101348"
    target: "https://doi.org/10.1016/j.iot.2024.101348"

  IOTINUUM:
    title: "IoTinuum: The IoT Computing Continuum"
    author:
      - ins: "C. Kamienski"
        name: "C. Kamienski"
      - ins: "I. Zyrianoff"
        name: "I. Zyrianoff"
      - ins: "L. F. Bittencourt"
        name: "L. F. Bittencourt"
      - ins: "M. Di Felice"
        name: "M. Di Felice"
    date: 2024
    seriesinfo:
      IEEE: "Proceedings of the 20th International Conference on Distributed Computing in Smart Systems and the Internet of Things (DCOSS-IoT), pp. 732-739"
      DOI: "10.1109/DCOSS-IoT61029.2024.00114"
    target: "https://doi.org/10.1109/DCOSS-IoT61029.2024.00114"

  MCP:
    title: "Model Context Protocol (MCP)"
    author:
      - org: "Agentic AI Foundation (AAIF)"
    date: 2026
    target: "https://aaif.io/projects/model-context-protocol"

  WOOLDRIDGE-AGENTS:
    title: "An Introduction to MultiAgent Systems"
    author:
      - ins: "M. Wooldridge"
        name: "M. Wooldridge"
    date: 2009
    seriesinfo:
      "John Wiley and Sons": "2nd Edition"

  WPIETF2025:
    title: "Smart Application Development and Deployment over the IoT Computing Continuum"
    author:
      - ins: "C. Kamienski"
        name: "Carlos Kamienski"
    date: 2025
    seriesinfo:
      "Proceedings of the 10th Pre-IETF Workshop (WPIETF 2025)": "Brazilian Computer Society (SBC), pp. 15-28"
      DOI: "10.5753/wpietf.2025.17508"
    target: "https://doi.org/10.5753/wpietf.2025.17508"

  METROAGRIFOR2025:
    title: "Distributed Smart Agriculture Monitoring over the IoT Computing Continuum"
    author:
      - ins: "C. Kamienski"
        name: "Carlos Kamienski"
      - ins: "I. Zyrianoff"
        name: "Ivan Zyrianoff"
      - ins: "L. Xue"
        name: "Lei Xue"
      - ins: "M. Di Felice"
        name: "Marco Di Felice"
    date: 2025
    seriesinfo:
      "2025 IEEE International Workshop on Metrology for Agriculture and Forestry (MetroAgriFor)": "pp. 406-411"
      DOI: "10.1109/MetroAgriFor66923.2025.11512449"
    target: "https://doi.org/10.1109/MetroAgriFor66923.2025.11512449"

--- abstract

Smart applications increasingly depend on the Internet of Things (IoT) and distributed computing environments spanning constrained devices, edge nodes, cloudlets, and cloud infrastructure, collectively known as the edge-cloud, or computing continuum. This document uses the term IoT computing continuum to highlight the importance of IoT-specific constraints and requirements within this broader context. Although prior work has addressed communication aspects and edge functions in these environments, as noted in RFC 9556 and comprehensive surveys of the computing continuum, there has been comparatively less focus on application-centric issues such as deployment, placement, and lifecycle management. This document identifies key challenges and conceptual considerations for deploying smart applications across the IoT computing continuum, aiming to provide a unified architectural perspective and vocabulary to guide ongoing research within the IRTF and inform future standardization initiatives.

--- middle

# Introduction

The Internet of Things (IoT) has evolved from simple data-collection systems into a foundation for complex, data-driven smart applications across domains such as smart cities, precision agriculture, industrial automation, and healthcare. These applications increasingly depend on distributed computing resources to sense, process, and act on data close to where it is generated, while also leveraging large-scale cloud infrastructures for coordination, analytics, and long-term storage.

This evolution has led to the emergence of a distributed computing environment spanning multiple stages, from highly constrained devices and gateways to edge nodes, cloudlets, and centralized cloud platforms. The literature commonly describes this environment as the edge-cloud continuum, IoT-edge-cloud continuum, or simply the computing continuum. Comprehensive perspectives on the evolution of this paradigm are provided in {{CONTINUUM-SURVEY}}. In this document, the term IoT computing continuum emphasizes the presence of constrained IoT devices and the domain-specific requirements they introduce.

Recent research and standardization efforts have highlighted this continuum and discussed challenges related to edge functions, data handling, and communication across heterogeneous environments, including IETF and IRTF work such as {{RFC9556}}. However, much of the existing discussion remains infrastructure- or communication-centric, with comparatively less focus on the implications for smart application deployment and lifecycle management.

From an application perspective, smart services are no longer confined to a single execution environment. Instead, they comprise multiple functions that must be placed, coordinated, and potentially migrated across stages of the IoT computing continuum to meet requirements for latency, resilience, scalability, privacy, and energy efficiency. In practice, these decisions are often handled manually or through ad hoc mechanisms, leading to fragmented solutions and limited portability across deployments.

The lack of a shared, application-centric view of deployment over the IoT computing continuum creates challenges for both researchers and practitioners. It complicates systematic reasoning about application structure, hinders the comparison of alternative approaches, and makes it difficult to identify common requirements that could inform future research and standardization activities.

This document contributes to this discussion by examining smart application deployment across the IoT computing continuum from a conceptual and architectural perspective. Rather than proposing specific mechanisms or protocols, it identifies key challenges, clarifies terminology, and outlines considerations relevant to ongoing research within the Thing-to-Thing Research Group (T2TRG) of the Internet Research Task Force (IRTF).

# Scope and Non-Goals

This document focuses on conceptual and architectural considerations for deploying smart applications across the IoT computing continuum. It addresses challenges, common patterns, and terminology arising from distributed application logic across heterogeneous computing environments, including constrained IoT devices, edge nodes, and cloud platforms. The intent is to support research-oriented discussion and provide a shared frame of reference for ongoing and future IRTF work. The discussion explicitly considers the interplay between application development and deployment, while remaining agnostic to specific tools, workflows, or operational practices.

The document does not specify concrete deployment mechanisms, protocols, or interfaces. It does not define a reference architecture or mandate how applications should be structured, deployed, or managed in practice. Instead, it describes the problem space and highlights issues relevant across multiple technologies, deployment models, and research efforts.

In particular, the following items are explicitly outside the scope of this document:

   *  The specification of new communication protocols, APIs, or data
      models.

   *  The definition of normative requirements, including the use of
      requirement keywords such as MUST, SHOULD, or MAY.

   *  The standardization of specific platforms, frameworks, or
      programming models for IoT application deployment.

   *  Performance evaluations or quantitative comparisons between
      alternative solutions. Where this document mentions quantitative
      results, it does so only by reference to published work.

By clearly delineating its scope and non-goals, this document complements existing and ongoing efforts in the computing continuum, including work on communication, edge functions, and operational aspects, while maintaining a technology-agnostic, application-centric perspective.

# Terminology

This document uses the following terms with the meanings indicated below. These definitions clarify usage in this document and are not meant to redefine existing terminology used elsewhere.

**Internet of Things (IoT):**
A system paradigm involving interconnected physical objects equipped with sensing, actuation, processing, and communication capabilities, operating under resource constraints, as discussed in {{RFC7452}}.

**Constrained Devices:**
Devices with limited processing power, memory, energy availability, or communication capabilities. The use of the term *constrained* in this document follows the terminology defined in {{I-D.ietf-iotops-7228bis}}.

**IoT Computing Continuum:**
A distributed execution environment spanning constrained IoT devices, edge nodes, cloud platforms, and network elements that provide suitable processing capabilities. Application functions may execute at different stages, depending on their requirements and the capabilities and constraints of each environment. These stages are not restricted to general-purpose computing hosts: programmable network elements can also execute eligible functions as part of the continuum, integrating the notion of Computing in the Network (COIN). The shorthand term *IoTinuum* has been used in related work to denote this same concept {{IOTINUUM}}. This document uses the expanded form throughout for clarity and alignment with terminology used in related standardization efforts.

**Edge Node:**
An intermediate computing node between constrained devices and centralized cloud infrastructure, providing computation, storage, and networking closer to data sources, as described in {{RFC9556}}.

**Orchestration and Choreography:**
Two coordination styles for distributed applications. Orchestration refers to coordination driven by explicit control logic, while choreography relies on decentralized interactions among components without a central coordinator.

# IoT Devices in the Geographical and Computing Continuum

Smart applications draw on data produced by large numbers of IoT sensors, and the infrastructures that support them are inherently distributed, both geographically and in terms of computing resources. Data typically follow an end-to-end path that begins with acquisition by sensors in the field, crosses one or more edge nodes that process, store, and forward them, and reaches cloud data centers that run physical or data-driven models and provide long-term storage. The resulting knowledge often travels back along that path as commands to actuators that change the physical environment's state. At the same time, users need to monitor the application, make decisions, and start recovery procedures from anywhere, using whatever terminal they prefer. IoT devices are therefore only one part of a system that spans the field, the network, and the cloud {{IOTINUUM}}.

This geographical and computing continuum is the setting in which the applications discussed in this document are deployed. {{continuum}} describes how the continuum has been characterized in existing research and in IETF and IRTF work, and how this document positions itself relative to that work. {{iot-specifics}} then identifies what changes for application deployment when constrained IoT devices are part of the continuum.

## The IoT Computing Continuum {#continuum}

The increasing distribution of computation across networked systems has led to what is commonly described as a computing continuum, spanning centralized cloud infrastructures, intermediate edge and fog nodes, and highly constrained end devices {{CONTINUUM-SURVEY}}. This paradigm reflects a shift away from strictly centralized processing models toward more distributed execution, driven by requirements related to latency, bandwidth efficiency, resilience, data locality, and regulatory constraints.

In the context of the Internet of Things (IoT), this continuum takes on additional characteristics that distinguish it from more general edge-cloud computing environments. IoT deployments involve large numbers of heterogeneous devices with severe resource constraints, intermittent connectivity, and close interaction with the physical world through sensing and actuation {{RFC7452}}. As a result, computation is often pushed closer to data sources not only for performance reasons, but also to enable timely control actions, reduce energy consumption, and preserve privacy.

Recent research and standardization activities have explored different aspects of this continuum. In particular, work within the IETF and IRTF has highlighted the importance of edge computing and discussed the functional components and challenges of operating across distributed environments {{RFC9556}}. Existing documents have examined edge functions for data processing, storage, and communication, as well as the roles of gateways and intermediate nodes in bridging constrained devices to cloud services. These efforts provide an important foundation for understanding the continuum's structural and operational properties.

This document takes a complementary, not competing, perspective. While {{RFC9556}} characterizes functional components and infrastructure-level challenges, focusing on edge functions and the communication fabric that supports them, this document shifts attention to the application layer that runs on top of that infrastructure. Specifically, it considers how smart applications, composed of multiple interdependent functions, are decomposed, placed, coordinated, and managed across the heterogeneous stages enabled by that infrastructure. Application-centric concerns such as functional decomposition, placement, coordination style, and lifecycle management are largely orthogonal to the infrastructure view and remain comparatively underexplored in current standardization discussions.

This document adopts the term *IoT computing continuum* to refer to this distributed execution environment, encompassing constrained IoT devices, edge nodes, cloud platforms, and network elements with processing capabilities. The continuum naturally accommodates Computing in the Network (COIN): application processing can include eligible functions executed within the network. For example, a programmable network element may execute filtering, aggregation, or preprocessing when its capabilities and the application semantics permit. This does not imply that every network element is programmable or that every application function is suitable for in-network execution. Building on existing work, this document focuses on how the properties of the IoT computing continuum influence application deployment, placement, and lifecycle management, rather than on defining specific technologies or architectural solutions.

## What Changes for Application Deployment in IoT {#iot-specifics}

Much of what this document discusses, such as functional decomposition, placement, migration, and coordination, applies to the general edge-cloud deployment process. This section states what changes when the application includes IoT devices.

Execution targets that cannot host general-purpose runtimes:
: Many devices at the edge of the continuum are microcontroller-class constrained devices {{I-D.ietf-iotops-7228bis}} that cannot run containers or virtual machines. They can host few functions, and those functions are often fixed when the firmware image is built. Placing or moving a function on such a device can therefore require a firmware update {{RFC9019}}, rather than a runtime operation.

Energy as a placement constraint:
: For battery-powered or energy-harvesting devices, the energy cost of computing and of transmitting data is part of the placement decision. Sleep cycles also mean that a device may be unreachable when a deployment action is issued.

Disconnection as a normal condition:
: Low-power radio links and rural settings make disconnection an expected operating condition rather than a failure. Functions that must keep working during disconnection must run on the device side of the link that may fail, and deployment actions must tolerate devices that are reachable only occasionally.

Coupling to the physical world:
: Sensing and actuation tie some functions to a specific location and device, so they cannot be migrated freely. Control loops bound how far from the device a function can execute. Because actuation has physical consequences, safe behavior during an update or migration has to be defined in advance.

Overlapping device and application lifecycles:
: Device firmware, edge services, and cloud functions evolve on different schedules and are often managed by different parties. An application update may depend on a firmware version, and the reverse.

Many administrative domains in a single deployment:
: One deployment may combine devices owned by an end user, gateways or edge nodes operated by an integrator or a cooperative, network infrastructure operated by a network operator, and cloud services from a provider. No single party controls all execution environments, which affects who may place, update, or migrate a function.

In general computing continuum deployments, execution environments are typically servers that can host any function, connectivity is assumed to be stable, and a single operator often controls the infrastructure. Each point above removes one of these assumptions, and together they explain why this document uses the term IoT computing continuum.

# An Application-Centric View of the Continuum

Traditional IoT architectures often treat applications as tightly coupled to specific execution environments, typically assuming fixed roles for devices, gateways, and cloud services. In the IoT computing continuum, this assumption no longer holds. Smart applications must be understood as distributed entities whose behavior emerges from the coordinated execution of multiple components across heterogeneous computing stages. An application-centric view is therefore essential for reasoning about deployment, adaptation, and lifecycle management in such environments.

## Applications as Distributed Functional Graphs {#graph}

From an application-centric perspective, smart applications can be modeled as collections of interdependent functions rather than as monolithic software artifacts. These functions interact through well-defined data and control dependencies, forming a logical application graph that captures the application's structure independently of where its components execute. This representation enables reasoning about application behavior, dependencies, and composition without prematurely binding functions to specific devices or platforms.

Viewing applications as distributed functional graphs is particularly relevant in IoT environments, where different functions may have distinct requirements for latency, computational resources, sensor or actuator access, and interaction with external services. By separating the application's logical structure from its physical deployment, this model supports more flexible placement and adaptation strategies across the continuum.

## Decoupling Application Logic from Execution Environments {#decoupling}

A key implication of the application-centric view is decoupling application logic from execution environments. Application functionality should be expressed independently of specific hardware platforms, operating systems, or runtime environments. This decoupling enables portability across heterogeneous devices and supports dynamic reassignment of application components as execution conditions change.

In the IoT computing continuum, execution environments vary widely in terms of resource availability, connectivity, and operational constraints. Binding application logic too early to a particular environment limits the ability to adapt to failures, load variations, or evolving requirements. An application-centric approach instead treats execution environments as abstract resources onto which application functions can be mapped, allowing deployment decisions to be revisited over time.

## Placement and Distribution Across the Continuum {#placement}

Once application logic is decoupled from execution environments, placing application functions becomes a first-class concern. Placement decisions determine where an application's functions execute within the IoT computing continuum, from constrained devices and gateways to edge nodes and cloud platforms. These decisions directly affect end-to-end application properties, including latency, reliability, energy consumption, and data locality.

## Application Lifecycle Beyond Initial Deployment {#lifecycle}

In centralized systems, application deployment is often treated as a one-time event followed by relatively infrequent updates. In contrast, the IoT computing continuum introduces a more complex and dynamic application lifecycle. Placement is therefore not static. Beyond initial deployment, applications may adapt continuously through updates, reconfiguration, scaling, component migration, and partial redeployment across different continuum stages, in response to changes in workload, network conditions, or operational context.

Managing this lifecycle is particularly challenging in IoT environments for the reasons listed in {{iot-specifics}}, especially overlapping device and application lifecycles and multiple administrative domains. Lifecycle management therefore encompasses not only software updates but also the ongoing coordination of distributed application components.

# Challenges in Smart Application Development and Deployment {#challenges}

The IoT computing continuum introduces challenges that fundamentally affect both the development and deployment of smart applications. Unlike centralized environments, where development and deployment can often be treated as loosely coupled phases, the heterogeneity, distribution, and dynamism of the continuum create strong interdependencies among application design choices, deployment decisions, and runtime behavior. As a result, development and deployment concerns cannot be addressed effectively in isolation.

A primary challenge stems from the bidirectional influence between application development and deployment constraints. Development decisions, such as functional decomposition, communication patterns, and state management, directly affect deployment feasibility across constrained devices, edge nodes, and cloud platforms.

At the same time, deployment realities, such as resource availability, network conditions, latency requirements, and energy constraints, often impose limitations that shape or even redefine application design. This mutual influence complicates traditional workflows that assume stable execution environments and defer deployment decisions until later.

Heterogeneity across the continuum further amplifies this challenge. Execution environments vary widely in hardware capabilities, operating systems, runtime support, and management interfaces. Developers must therefore anticipate deployment diversity early in development, while deployment mechanisms must accommodate application abstractions that span multiple platforms. Without integrated development and deployment considerations, solutions tend to become fragile, tightly coupled to specific environments, and difficult to evolve.

Because deployment is an ongoing process ({{lifecycle}}), runtime behavior must also feed back into development-time assumptions, which static deployment models and rigid application designs do not support.

These challenges align with principles commonly associated with DevOps practices, which emphasize continuous integration, continuous deployment, and feedback loops between development and operations. However, transferring DevOps concepts to the IoT computing continuum is non-trivial. Conventional DevOps pipelines typically target cloud-centric environments and assume homogeneous infrastructure, reliable connectivity, and centralized control. The IoT computing continuum removes each of these assumptions ({{iot-specifics}}).

Finally, the lack of shared abstractions and terminology for reasoning about development and deployment across the continuum makes it difficult to compare approaches and identify common requirements. When the interplay between development and deployment is not made explicit, solutions often remain ad hoc and platform-specific.

# Conceptual Deployment Model

This section outlines a conceptual model for reasoning about the deployment of smart applications across the IoT computing continuum. The model supports analysis and discussion rather than prescribing specific mechanisms, architectures, or workflows. It provides a shared abstraction that captures how application structure, execution environments, and coordination mechanisms interact in heterogeneous, dynamic IoT scenarios.

The model builds on the application graph ({{graph}}) and on the separation between application logic and execution environments ({{decoupling}}). Execution environments are characterized by capabilities, constraints, and operational context, such as computational power, connectivity, proximity to data sources, and energy availability. Deployment maps the functions of the application graph onto execution environments. This mapping determines where functions execute, but it does not, by itself, define how they coordinate during execution, so deployment decisions must be considered together with coordination strategies.

Execution environments can include programmable network elements as well as general-purpose computing nodes. Placement therefore selects both a location and a type of execution environment. A function is eligible for execution within the network only if the element supports its computation, state, data access, and interaction requirements. Constraints on the processing model, memory, persistent state, and management interfaces can make only part of an application suitable for such placement. Network forwarding responsibilities and application processing may also share resources, so deployment feasibility depends on their interaction.

Application components can coordinate in different ways, most notably through orchestration and choreography. In an orchestration style, explicit control logic drives coordination by managing execution order, data flow, and component interactions. This style provides a global view of application behavior and can simplify reasoning about end-to-end execution, but it may introduce centralization and scalability concerns in highly distributed environments. In contrast, choreography relies on local interactions and shared interaction rules, letting components coordinate in a decentralized way without a single point of control. This style can improve scalability and resilience, but it may complicate global reasoning and debugging.

The choice between orchestration and choreography, or combinations thereof, is closely tied to deployment decisions and to the characteristics of the IoT computing continuum. Resource constraints, network conditions, mobility, and administrative boundaries may favor one coordination style over another at different stages of the continuum. Moreover, coordination strategies may need to evolve over time as applications adapt to changing conditions, reinforcing the dynamic nature of deployment.

The model therefore treats placement, coordination, and lifecycle management as interrelated concerns. Adapting the coordination strategy is a lifecycle operation in {{lifecycle}}, and runtime observations, including performance metrics and failure events, feed back into both deployment decisions and application design ({{challenges}}).

# Illustrative Scenarios

We present two illustrative scenarios that ground the conceptual deployment model discussed earlier. The scenarios demonstrate how application-centric concepts, deployment decisions, and coordination styles manifest in realistic settings, without prescribing specific technologies or architectures. The first scenario describes a smart irrigation application deployed in operational agricultural settings, providing a concrete reference for placement and lifecycle concerns under real-world constraints. The second scenario describes a drone-based delivery application that spans a broader range of continuum stages and exhibits a richer interplay between coordination styles.


## Smart Irrigation in Precision Agriculture

This scenario is grounded in the SWAMP platform {{SWAMP}}, which describes an IoT-based precision-irrigation architecture and deployments for four pilots in Brazil and Europe. Its configurable distribution of components across cloud and farm-side fog resources supports the discussion of deployment diversity and reuse across farms. In particular, the MATOPIBA deployment description includes local processing and resilience to Internet disconnections. {{METROAGRIFOR2025}} revisits the MATOPIBA irrigation application, maps its functions onto continuum stages from field devices to farm-side fog and cloud, and qualitatively evaluates a continuum-aware development and deployment framework on that use case. The placement and lifecycle considerations below build on that operational motivation and are not a claim that either paper evaluates every adaptation mechanism discussed here.

Smart irrigation applications collect environmental data, such as soil moisture and weather conditions, and use it to determine how much, when, and where to irrigate. In operational deployments, these applications typically span constrained field sensors, low-power gateways that act as radio concentrators, on-premises edge nodes in farm facilities, and cloud services for analytics, forecasting, and long-term storage. End users interact with the application through mobile or web interfaces to inspect data and approve irrigation plans.

From an application-centric perspective, the irrigation scenario exemplifies how functional decomposition maps naturally onto multiple continuum stages. Sensing and local preprocessing functions execute on constrained devices and field gateways. Intermediate functions, such as data filtering, sensor calibration, and disconnection resilience, run on on-premises edge nodes near the irrigation infrastructure and remain operational even when cloud connectivity is unavailable. More computationally intensive functions, including data fusion, soil moisture forecasting, and irrigation optimization, run on cloud platforms that offer greater resources and broader data visibility.

A defining property of this scenario is the need to keep operating with intermittent wide-area connectivity, common in rural deployments. Functions on on-premises edge nodes must sustain essential behavior when cloud services are temporarily unreachable, such as enforcing safety thresholds or running simplified local models, and reconcile state once connectivity is restored. This requirement directly shapes how developers decompose application functions and where they deploy them, illustrating the bidirectional influence between development and deployment concerns discussed earlier.

Over time, functions may be updated or extended to incorporate new models or new sensor modalities, and the same application logic may need to be deployed across farms with different infrastructure configurations. This deployment diversity is what motivated the configurable distribution of components in {{SWAMP}}.

## Drone-Based Delivery in Urban Environments

The delivery-service setting and the need for autonomous local collision avoidance are motivated by {{DRONE-DELIVERY}}. That study evaluates non-cooperative geometric collision-avoidance strategies through simulation and analytical modeling, and explains why local strategies remain relevant when communication is unavailable or emergency detours are needed. The distribution of functions across edge nodes, cloudlets, and cloud platforms described below is an illustrative deployment extension; it is not an experimentally validated architecture from that study. In particular, autonomous non-cooperative avoidance is not choreography, which concerns interactions among components.

A drone-based delivery application uses unmanned aerial vehicles to deliver packages in urban areas. The application comprises multiple functional components, including mission planning, navigation, sensing, local coordination, and backend services for order management and analytics. From an application-centric perspective, these components form a logical application graph, with dependencies reflecting data flows and control interactions among functions. The application operates across the full span of the IoT computing continuum, leveraging constrained onboard devices, nearby edge nodes, operator-provided cloudlets, and cloud platforms.

Low-level sensing, actuation, and real-time navigation run directly on the drone because of strict latency and control requirements. Local coordination and situational awareness functions may execute on nearby edge nodes or gateways that aggregate information from multiple drones operating in the same area. Operator-provided cloudlets, for example, those associated with 5G or future 6G infrastructure, can host functions that support cooperative behavior among drones, such as collision avoidance assistance and shared situational awareness. Backend services, including mission planning, optimization, logging, and analytics, typically run on cloud platforms that provide greater computational resources and global system visibility.

This scenario particularly illustrates the coexistence of different coordination styles within a single application. Mission planning and high-level task assignment naturally follow an orchestration style, in which a centralized component coordinates delivery schedules and routes based on global system state. In contrast, local interactions among drones, such as collision avoidance or cooperative sensing, follow a choreography style, relying on decentralized interactions and shared interaction rules without a single controlling entity. Both coordination styles coexist within the same application and are influenced by deployment choices across the continuum, demonstrating that the distinction between orchestration and choreography is not merely theoretical but reflects concrete architectural trade-offs.

Deployment decisions in this scenario are also inherently dynamic. As drones move through different environments or face changing network conditions, mappings of coordination functions to edge nodes or cloudlets may need revision, while backend services remain centralized. Components may also be updated, reconfigured, or migrated in response to changes in delivery demand, individual drone failures, or variations in network availability.

## Discussion

Together, these two scenarios illustrate the spectrum of smart applications operating across the IoT computing continuum. The first grounds the discussion in operational deployments with documented constraints, particularly around intermittent connectivity and the need for resilient edge behavior. The second reveals the broader architectural space where placement, coordination, and lifecycle concerns fully manifest, including the explicit coexistence of orchestration and choreography within a single application. Both share the fundamental property that application behavior emerges from the coordinated execution of distributed functions across heterogeneous stages, reinforcing the need for application-centric perspectives on deployment and lifecycle management.

# The Role of AI Agents in Application Deployment {#agents}

The previously discussed conceptual deployment model treats placement, coordination, and lifecycle management as interconnected, inherently dynamic concerns. As the scale, heterogeneity, and dynamism of the IoT computing continuum increase, addressing these concerns through static policies or manual procedures becomes increasingly challenging, especially when application workloads exhibit heterogeneous, context-sensitive behavior. AI agents, defined as autonomous software entities that can perceive their environment, reason about objectives, and act on deployment infrastructure, offer a promising solution for managing this complexity. Foundational research on multi-agent systems {{WOOLDRIDGE-AGENTS}} offers established abstractions for understanding agent behavior. This section analyzes the role of such agents from an application-centric perspective, without specifying particular agent architectures, frameworks, or protocols.

AI agents are connected to application deployment in two complementary ways. First, agents can facilitate deployment by assisting with or automating decisions about the placement, coordination, adaptation, and lifecycle management of application functions. Second, agents are software components that must run within the continuum. Therefore, their deployment must also be considered under the same placement criteria as application functions. The following discussion examines these two roles sequentially.

## Agents as Enablers of the Deployment Process

In this first role, AI agents support deploying the services that comprise a smart application across the IoT computing continuum. Given a logical application graph and a set of available execution environments, agents can evaluate candidate mappings of functions to continuum stages, considering application-level requirements such as latency, resilience, energy consumption, and data locality, as well as runtime observations of infrastructure conditions. Beyond initial placement, agents can drive lifecycle operations, including reconfiguration, scaling, migration, and partial redeployment, in response to workload variations, mobility, connectivity disruptions, or evolving physical contexts.

A concrete example is deploying inference workloads based on large language models, where placement decisions must account for response quality, response time, and the availability of each candidate execution environment. Whether adaptive placement, agent-driven or not, outperforms a simple static configuration is an open question. The answer depends heavily on how accurately the placement logic estimates the availability of each environment: under intermittent connectivity in particular, inaccurate estimates can lead to worse outcomes than a static choice. The authors are currently investigating these trade-offs.

Agent-assisted deployment does not presuppose a particular coordination style. A single agent with global visibility may coordinate deployment decisions in an orchestration style, while multiple agents interacting through shared rules may realize deployment coordination in a choreography style. The Model Context Protocol {{MCP}} supports interactions between applications and tools or contextual resources, while the Agent2Agent protocol {{A2A}} supports interactions among agents. Neither protocol, by itself, determines whether an application follows orchestration, choreography, or a hybrid arrangement; that choice depends on the distribution of coordination logic and decision authority.

The IETF Agent Communication Protocols (agentproto) Working Group {{AGENTPROTO}} addresses a complementary concern: the correlation, lifecycle, and continuity of agentic dialogs across participants, intermediaries, and trust boundaries. These capabilities matter when deployment agents exchange observations and actions across the continuum, including when an interaction resumes after interruption, or a participant changes network attachment. Dialog management does not itself preserve application state or guarantee the completion of a deployment action. The group's charter does not standardize agent decision-making or planning semantics, and therefore does not determine placement policies or the application's coordination style.

Agents distributed across the continuum may exchange information on local resource availability, observed conditions, and pending deployment actions. These interactions can combine local knowledge available near constrained devices with global objectives maintained on cloud platforms. Their use requires distinguishing communication and dialog continuity from the application-level rules that govern deployment decisions and recovery.

## Deployment of the Agents Themselves

In their second role, agents function as deployable entities. As software components, they require execution environments that provide sufficient computational power, memory, and connectivity. Agents can operate anywhere in the IoT computing continuum, including gateways, edge nodes, cloudlets, and cloud platforms. The selected deployment stage influences the timeliness of agent decisions, the degree of local context awareness, and resilience to connectivity disruptions.

Constrained devices require special consideration, as many lack sufficient resources to support a full agent runtime. Nevertheless, deployment strategies must often account for device-level conditions. A proxy-based approach addresses this challenge: a lightweight proxy on the constrained device represents it to a nearby agent, such as a gateway or edge node, which then reasons on the device's behalf. This method enables agent-based deployment at even the most resource-limited stages of the continuum, while adhering to the constraints outlined in {{I-D.ietf-iotops-7228bis}}.

Agent deployment is recursive: the mechanisms agents use to deploy application functions also apply to the agents themselves. The placement, migration, and lifecycle management of agents present challenges analogous to those for application components, but they also raise additional concerns about trust, accountability, and control, especially when agents operate autonomously across multiple administrative domains. {{research-directions}} identifies open questions associated with this dual role.


# Relationship to Ongoing Research and Standardization

The issues discussed in this document build on existing research and standardization efforts on edge computing and the computing continuum, including work within the IETF and IRTF (e.g., {{RFC9556}}) and broader academic perspectives (e.g., {{CONTINUUM-SURVEY}}). Within the IRTF, the T2TRG has explored programmability, coordination, and interoperability among connected devices.

Several concrete research efforts have examined application-centric aspects of the IoT computing continuum and informed the perspective adopted in this document. Work on the notion of an IoT computing continuum as a unifying framework for reasoning about development and deployment choices has clarified the role of distributed application stages {{IOTINUUM}}. Complementary work on deployment-aware approaches, such as IoTDeploy, has explored how application components can be systematically placed and migrated across continuum stages while preserving application-level properties {{IOTDEPLOY}}. More recent efforts have investigated integrated frameworks for developing and deploying continuum-aware smart applications {{WPIETF2025}} {{METROAGRIFOR2025}}, providing concrete examples of how application-centric abstractions can be realized in practice. These efforts are cited here as representative of ongoing work in the area, not as prescriptive references, and this document remains agnostic to specific frameworks or implementations.

Community-driven efforts, including workshops focused on future Internet research, have also discussed application deployment over the IoT computing continuum in the context of IETF and IRTF engagement, as exemplified by {{WPIETF2025}}. This document complements these efforts by taking an application-centric view of deployment and lifecycle management.

## Device Update, Discovery, and Management

The SUIT firmware update architecture {{RFC9019}} addresses secure firmware updates for IoT devices. It provides lifecycle foundations for device software, while application deployment raises additional questions about compatibility and coordinated transitions across device firmware, edge services, and cloud functions.

CoRE work provides complementary mechanisms. The Resource Directory {{RFC9176}} supports resource registration and lookup, including for endpoints that cannot remain continuously available. The CoAP Management Interface (CORECONF) {{I-D.ietf-core-comi}}, a CoRE working group document, is relevant to accessing management data in constrained environments. Resource discovery and management can provide inputs and operations for deployment, but they do not, by themselves, describe an application's entire dependency graph or determine a safe multi-component transition. Investigating how to compose existing mechanisms is preferable to assuming a new management interface is needed.

## Computing in the Network and Intent

The IoT computing continuum can naturally integrate Computing in the Network (COIN), with eligible application functions executing in processing-capable network elements. Work in COINRG {{COINRG}} explored using network resources for computation and the relationship between computing and networking. From this application-centric perspective, a network element with suitable processing capabilities can serve as an execution environment for an application function. This extends placement beyond choosing among device, edge, and cloud hosts to considering processing within the network itself.

For example, an application may place filtering, aggregation, or preprocessing in a programmable network element while retaining other functions on devices, edge hosts, or cloud platforms. Such a placement is conditional on execution capabilities, application semantics, resource limits, and administrative permissions. The connection to COIN is therefore part of the deployment model: the application graph can be mapped onto heterogeneous environments that include both computing hosts and processing-capable network elements. No particular in-network programming model or protocol is prescribed.

This connection is distinct from the relationship to CoRE described above. CoRE discovery and management mechanisms are relevant to finding and managing constrained resources and their interfaces. On the other hand, COIN concerns using network elements as execution environments. The two perspectives can complement each other, but the model does not assume that an in-network execution environment exposes a CoRE interface.

NMRG's work on intent-based networking, including the concepts and definitions in {{RFC9315}}, is relevant to expressing desired outcomes separately from operational actions. A research question here is how application objectives, such as retaining local behavior during disconnection, can be translated into deployment constraints and checked against observed behavior. This document does not specify such a mapping.

## Agent Communication and Dialog Management

The agentproto Working Group {{AGENTPROTO}} is chartered to define a baseline agentic dialog management protocol and a reference architecture integrating related protocol building blocks. Its scope includes dialog identifiers, lifecycle semantics, and propagation of dialog context over existing IETF protocols. Here, dialog context refers to identifiers and lifecycle state used for correlation and continuity, rather than model prompts, retrieved documents, or conversation memory.

This work is relevant to agents that coordinate deployment across heterogeneous execution environments and administrative boundaries. Correlating interactions and maintaining dialogs through interruptions can support exchanges among agents, operators, and tools in either orchestrated or choreographed applications. The relationship is complementary: this document considers which functions and agents execute where, how their responsibilities are coordinated, and how application behavior is preserved. Agentproto addresses interoperability of the dialogs used in those interactions. Its charter explicitly leaves agent decision-making and planning semantics outside its scope and does not replace application-layer protocols such as MCP or A2A. A migration of an application function or agent therefore still requires separate handling of execution state, authority, and application recovery.

## Descriptions of Things and Application Abstractions

The Semantic Definition Format (SDF) {{RFC9880}} describes data and interaction models of Things. W3C WoT Thing Descriptions {{WOT-TD}} describe Things and their interaction affordances, including information used to access those interactions. Both are candidates for reuse when describing the device-facing capabilities on which application functions depend.

Neither is treated here as a complete deployment language. Open questions include how such descriptions can be related to function dependencies, runtime requirements, permissible placements, state migration, and degraded operation. The appropriate reuse, composition, or extension of existing descriptions requires investigation before proposing new application-centric abstractions.

# Research Directions

The challenges and conceptual considerations discussed in this document point to several open research directions for smart application development and deployment across the IoT computing continuum. These directions are not exhaustive. Instead, they highlight areas that require further investigation to better understand how application structure, deployment decisions, coordination strategies, and lifecycle management interact in heterogeneous and dynamic environments.

One research direction concerns defining application-centric abstractions for deployment. This investigation can start with existing descriptions of Things, including SDF {{RFC9880}} and WoT Thing Descriptions {{WOT-TD}}, and assess which deployment information can be reused and which is still missing. While existing work has extensively explored infrastructure-level aspects of edge and continuum computing, a clear need remains for abstractions that let applications express functional decomposition, dependencies, and non-functional requirements independently of specific execution environments. Such abstractions would enable more systematic reasoning about placing, migrating, and adapting application components across stages of the IoT computing continuum, complementing existing architectural perspectives on edge computing {{RFC9556}} and broader analyses of the computing continuum {{CONTINUUM-SURVEY}}.

A second research direction concerns models, methodologies, and tools for the development--deployment interdependence described in {{challenges}}, including feedback loops between design-time assumptions and runtime observations, building on early deployment-aware approaches such as {{IOTDEPLOY}}.

Coordination strategies for distributed applications constitute another important research direction. Orchestration and choreography are complementary styles for coordinating distributed application components, each with distinct trade-offs in scalability, resilience, observability, and manageability. Understanding how to combine, adapt, or dynamically transition these coordination styles as applications evolve and deployment conditions change remains an open problem. This includes investigating how coordination strategies interact with placement decisions, fault handling, and lifecycle operations across heterogeneous execution environments in the IoT computing continuum.

Automation of deployment and lifecycle management is another research area. Manual deployment, configuration, and adaptation do not scale under the conditions described in {{iot-specifics}}. Automated, declarative, or policy-driven approaches, including the agent-based approaches in {{agents}}, need to remain transparent, controllable, and aligned with application-level objectives. Open questions include: a) how agent responsibilities should be distributed between application-level and infrastructure-level concerns; b) how inter-agent interactions can be made secure, auditable, and aligned with Internet architectural principles, particularly across administrative domains (see also {{security-considerations}}); c) how orchestration and choreography styles may be combined dynamically in agent-based deployment; d) how the placement and lifecycle of the agents themselves, including proxy-based representation of constrained devices, can be managed without introducing new points of fragility or centralization. Interaction frameworks such as {{MCP}} and {{A2A}} are still evolving, and their fit with application-centric deployment models remains to be assessed.

Finally, a shared vocabulary for application-centric deployment and lifecycle management is needed to compare research results across efforts and to identify where future IRTF or IETF work may be beneficial.

# Security Considerations

This document does not specify protocols, mechanisms, or architectures and therefore does not directly introduce new security vulnerabilities. However, the concepts discussed have important security implications worth considering.

In the IoT computing continuum, application components are distributed across heterogeneous and potentially untrusted execution environments, increasing the attack surface and complicating traditional security assumptions. Deployment decisions influence trust boundaries, data exposure, and the ability to isolate faults or compromised components. Remote attestation {{RFC9334}} is one way placement decisions can incorporate evidence about the state of a candidate execution environment, although many constrained devices lack the hardware support it requires.

Coordination strategies also have security implications. Orchestration-based approaches may introduce centralized control points that attackers can target, while choreography-based approaches rely on decentralized interactions that require robust authentication, authorization, and trust management among components.

The tight coupling between development and deployment further emphasizes the need to consider security throughout the application lifecycle. Deployment changes, component migration, or runtime adaptation can invalidate design-time assumptions about trust, isolation, and access control. As a result, security considerations must be revisited whenever application structure, placement, or coordination strategies evolve.

Agents that place or migrate functions ({{agents}}) introduce two additional considerations. The first is authorization. When an agent acts on behalf of a party, any placement or migration spanning administrative domains requires each affected domain to verify who authorized the agent, for which functions and execution environments, and for how long the authorization is valid. Delegation mechanisms such as OAuth 2.0 Token Exchange {{RFC8693}} and their adaptation for constrained environments in ACE {{RFC9200}} may provide a means to express such scoped authority. However, whether they are adequate for agent-initiated deployment actions is still unclear. The second consideration is accountability. Autonomous deployment decisions need to be recorded, along with the observations and objectives that led to them, so operators in each affected domain can review them afterward. Transparency logs of signed statements, as defined for digital supply chains in {{RFC9943}}, suggest one possible model, but whether it suits deployment decisions remains an open question.

Finally, the distributed, multi-domain nature of the IoT computing continuum raises challenges in identity management, secure communication, and policy enforcement across administrative boundaries. While this document does not address these challenges, they underscore the need to integrate security considerations into research and standardization efforts for application-centric deployment and lifecycle management.


# IANA Considerations

This document has no IANA actions.


# Acknowledgments

The authors acknowledge CGI.br (Brazilian Internet Steering Committee) for supporting their participation in the IETF/IRTF program, which enabled engagement in research and discussions within the Internet Research Task Force (IRTF).

The authors thank Ari Keränen for reviewing earlier versions of this document.
