---

title: "Application-Centric Considerations for Deployment over the IoT Computing Continuum"
abbrev: "IoTinummDeploy"
category: info

docname: draft-kamienski-iot-deployment-latest
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



