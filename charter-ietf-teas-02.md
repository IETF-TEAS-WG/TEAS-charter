The Traffic Engineering Architecture and Signaling (TEAS)
Working Group is responsible for defining IP, MPLS and GMPLS
traffic engineering architecture and identifying required
related control-protocol functions, i.e., routing and path
computation element functions. The TEAS group is also
responsible for standardizing RSVP-TE signaling protocol
mechanisms that are not related to a specific switching
technology.

Traffic Engineering (TE) is the term used to refer to
techniques that enable operators to control how specific
traffic flows are treated within their networks. TE is
applied to packet networks via MPLS TE tunnels and LSPs, but
may also be provided by other mechanisms such as forwarding
rules similar to policy-based routing. The MPLS-TE control
plane was generalized to additionally support non-packet
technologies via GMPLS. RSVP-TE is the signaling protocol
used for both MPLS-TE and GMPLS. Centralized and logically
centralized control models are also supported, e.g., via
Abstraction and Control of Traffic Engineered Networks (ACTN)
and stateful-PCE.

The TEAS WG is responsible for:

    a) Traffic-engineering architectures for generic
       applicability across packet and non-packet
       networks. This includes, for example, networks that
       perform centralized computation and control, distributed
       computation and control, or even a hybrid approach.

    b) Definition of protocol-independent metrics and
       parameters (measurement and/or service attributes) for
       describing links and tunnels/paths required for traffic
       engineering (and related routing, signaling and path
       computation). These will be developed in conjunction
       with requests and requirements from other WGs to ensure
       overall usefulness.

    c) Functional specification of extensions for routing
       (OSPF, ISIS) and for path computation (PCEP), including
       those that provide general enablers of
       traffic-engineering systems that may also use
       RSVP-TE. Protocol formats and procedures that embody
       these extensions will be done in coordination with the
       WGs supervising those protocols.

    d) Functional specification of generic (i.e., not data
       plane technology-specific) extensions for RSVP-TE, and
       the associated protocol formats and procedures that
       embody these extensions.

    e) Definition of control plane mechanisms and extensions to
       allow the setup and maintenance of TE paths and TE
       tunnels that span multiple domains and/or switching
       technologies, where a domain may be an IGP area, an
       Autonomous System, or any other region of topological
       visibility.

    f) Definition and extension of management and security
       techniques for TE path and tunnel control. This
       includes configuring and monitoring RSVP-TE as well as
       mechanisms used to configure, control, and report OAM
       within TE networks. YANG and MIB modules may be
       considered.
The TEAS working group is chartered to deliver the following:

    1. Definition of additional abstract service, link, and
       path properties such as jitter, delay, and
       diversity. Extensions to IGPs to advertise these
       properties, and extensions to RSVP-TE to request and to
       accumulate these properties. Work with PCE WG to include
       these properties in computation requests.

    2. Specification of terminology, architecture, and protocol
       requirements for abstraction and distribution of TE
       information between interconnected TE domains/layers.

    3. Specification and protocol extensions for a GMPLS
       External Network-to-Network Interface (E-NNI), i.e.,
       multi-domain GMPLS support.

    4. Protocol mechanisms to signal associated LSPs in
       particular with different source nodes.

    5. Requirements and protocol extensions for additional
       protection mechanisms including, for example, end-point
       protection, protection of P2MP LSPs, and inter-domain
       protection.

    6. YANG models in support of Traffic Engineering, in
       coordination with working groups working on YANG models
       for network topology and for technology-specific network
       attributes.
Requirements may be documented in stand-alone RFCs, may be
folded into architecture or solutions RFCs, may be recorded
on a wiki, or may be documented in an Internet-Draft that is
not progressed to RFC.

The TEAS WG will coordinate with the following working
groups:

    - With the MPLS WG to maintain and extend MPLS-TE protocol
      mechanisms and to determine whether they should be
      generalized.

    - With the CCAMP WG to maintain and extend non-packet, data
      plane technology-specific TE protocol mechanisms and to
      determine whether they should be generalized.

    - With the LSR (OSPF and ISIS) WG to maintain or extend TE
      routing mechanisms.

    - With the PCE WG on uses of a PCE in the
      traffic-engineering architecture, on PCE extensions per
      the above, and on RSVP-TE extensions to support PCE WG
      identified requirements.

    - With the IDR WG on the use of BGP-LS in TE environments.

    - With the DetNet WG on mechanisms (YANG models and
      protocols) to support DetNets.

    - With the SPRING WG on TE architecture and, where
      appropriate, TE-related protocol extensions.

    - With the SFC WG on mechanisms (YANG models and protocols) to
      support SFCs
In doing this work, the WG will cooperate with external SDOs
(such as the ITU-T and the IEEE 802.1) as necessary.
