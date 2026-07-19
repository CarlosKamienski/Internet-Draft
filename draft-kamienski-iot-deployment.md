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

Internet of Things (IoT):
A system paradigm involving interconnected physical objects equipped with sensing, actuation, processing, and communication capabilities, operating under resource constraints, as discussed in [RFC7452].

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
