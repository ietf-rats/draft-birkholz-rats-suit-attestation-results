---
title: Trustworthiness Vectors for the Software Updates of Internet of Things (SUIT) Workflow Model
abbrev: SUIT TV
docname: draft-birkholz-rats-suit-attestation-results-latest
category: std

ipr: trust200902
area: Security
workgroup: RATS
keyword: Internet-Draft

stand_alone: yes
pi:
  rfcedstyle: yes
  toc: yes
  tocindent: yes
  sortrefs: yes
  symrefs: yes
  strict: yes
  comments: yes
  inline: yes
  docmapping: yes
  toc_levels: 4

author:
 - ins: H. Birkholz
   name: Henk Birkholz
   organization: Fraunhofer SIT
   email: henk.birkholz@sit.fraunhofer.de
 - ins: B. Moran
   name: Brendan Moran
   organization: Arm Limited
   email: Brendan.Moran@arm.com

normative:
  RFC2119:

informative:
  I-D.ietf-rats-architecture: rats
  I-D.ietf-suit-manifest: suit
  I-D.ietf-teep-architecture: teep
  I-D.voit-rats-trusted-path-routing: tpr

--- abstract

The IETF Remote Attestation Procedures (RATS) architecture defines an output of the appraisal process that assesses trustworthiness of remote peers: Attestation Results.
Based on the Trustworthiness Vectors defined in Trusted Path Routing, this document defines a core set of Claims representing Attestation Results for the SUIT Workflow Model.
Consecutively, this document is in support of the Trusted Execution Environment Provisioning (TEEP) architecture, which defines the assessment of remote peers via RATS and uses SUIT as a remediation measure to improve trustworthiness of given remote peers. 

--- middle

# Introduction

Attestation Results are an essential output Verifiers as defined in the Remote ATtestation procedureS (RATS) architecture {{-rats}}.
They are consumed by Relying Parties: the entities that intend to build future decisions on assessments of trustworthiness.
Attestation Results must be easily digestable by Relying Parties -- in contrast to the rather complex or domain-specific Evidence digested by Verifiers.

This document focuses on Attestation Results that reflect the operational state of software components installed on hardware components and the outcomes of a corresponding Software Updates for Internet of Things (SUIT) Workflow Model {{-suit}}.
In order to create Attestation Results about an Attester's current installed software and latest update procedures, Attesters must be able to create corresponding Evidence to be appraised by Verifiers.

An update workflow in SUIT passes several stages with results that can range from informational notifications to critical errors.
Additionally, certain prerequisites defined in the SUIT Update Workflow Model must be satisfied, such as validated integrity and verified applicability of a SUIT manifest, or resolved dependencies for an update procedure.

This document highlights existing Claims about dependencies as defined in Trusted Path Routing {{-tpr}} that are applicable to the operational state of installed software and update prerequisites.
Additionally, this document defines new Claims that are specific to Command Sequence definitions in SUIT manifests.

 and Update Workflow and defines 
 to be used in the Trusted Execution Environment Provisioning (TEEP) architecture.

## Terminology

This document uses the terms and concepts defined in {{-rats}}, {{-suit}}, and {{-teep}}.

{::boilerplate bcp14}

# Trustworthiness Vectors

While there are usage scenarios where Attestation Results can be a binary decisions, more often than not the assessment of trustworthiness is a fine grained spectrum or based on multiple factors. These shades of Attestation Results are captured by the definition of Trustworthiness Vectors in Trusted Path Routing {{-tpr}}. Trustworthiness Vectors are sets of Claims representing appraisal outputs created by a Verifier. Each of these Claims is called a Trustworthiness Level. Multiple Trustworthiness Level are composed into a vector.

--- back
