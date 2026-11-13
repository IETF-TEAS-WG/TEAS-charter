The Traffic Engineering Architecture and Signaling (TEAS) Working Group is responsible for defining IP, MPLS, Segment Routing, and GMPLS traffic engineering architecture and identifying required related control-protocol functions, i.e., routing and path computation element functions. The TEAS group is also responsible for standardizing RSVP-TE signaling protocol mechanisms that are not related to a specific switching technology.

Traffic Engineering (TE) is the term used to refer to techniques that enable operators to control how specific traffic flows are treated within their networks. TE is applied to packet networks via MPLS TE tunnels and LSPs, via SR policies and paths (SR-MPLS and SRv6), via IP TE Tunnels, and may also be provided by other mechanisms such as forwarding rules similar to policy-based routing. The MPLS-TE control plane was generalized to additionally support non-packet technologies via GMPLS. RSVP-TE is the signaling protocol used for both MPLS-TE and GMPLS. Centralized and logically centralized control models are also supported, e.g., via Abstraction and Control of Traffic Engineered Networks (ACTN) and stateful-PCE. TE mechanisms also underpin the realization of IETF Network Slices. TE is also increasingly expected to be power-aware, i.e., to take the power consumption of network resources into account when computing and placing paths.

The TEAS WG is responsible for:

- a) Traffic-engineering architectures for generic applicability across packet and non-packet networks. This includes, for example, networks that perform centralized computation and control, distributed computation and control, or even a hybrid approach.
- b) Definition of protocol-independent metrics and parameters (measurement and/or service attributes) for describing links and tunnels/paths required for traffic engineering (and related routing, signaling and path computation). These will be developed in conjunction with requests and requirements from other WGs to ensure overall usefulness.
- c) Functional specification of TE specific extensions for link-state routing (OSPF, ISIS, BGP-LS) and for path computation (PCEP), including those that provide general enablers of traffic-engineering systems that may also use RSVP-TE. Protocol formats and procedures that embody these extensions will be done in coordination with the WGs supervising those protocols.
- d) Functional specification of generic (i.e., not data-plane technology-specific) extensions for RSVP-TE, including support for new forwarding planes, and the associated protocol formats and procedures that embody these extensions.
- e) Definition of control plane mechanisms and extensions to allow the setup and maintenance of TE paths and TE tunnels that span multiple domains and/or switching technologies, where a domain may be an IGP area, an Autonomous System, or any other region of topological visibility.
- f) Definition and extension of management and security techniques for TE path and tunnel control. This includes configuring and monitoring RSVP-TE, security of RSVP-TE signaling, as well as mechanisms used to configure, control, and report OAM and telemetry within TE networks. YANG modules will be developed as appropriate.
- g) Architecture, realization, and management of IETF Network Slices and Network Resource Partitions (NRPs), building on RFC 9543.

The TEAS working group is chartered to deliver the following:

1. Development of YANG models in support of Traffic Engineering (TE tunnels and LSPs, TE topologies including MPLS-TE and Layer 3 TE, RSVP, TE and service mapping, path computation), in coordination with working groups working on YANG models for network topology and for technology-specific network attributes.
2. Development of ACTN applicability documents and models, including packet optical integration, service assurance, and telemetry.
3. Maintenance of previously delivered TE architecture and RSVP-TE specifications (including the abstraction and distribution of TE information between domains, GMPLS E-NNI, associated LSPs, and protection), and requirements and protocol extensions for additional protection mechanisms as needed.
4. RSVP-TE enhancements, covering scalability, security, and extensions to realize distributed bandwidth management over different forwarding planes.
5. Architecture, YANG data models, and applicability documents for IETF Network Slice Services, Network Resource Partitions and their realization in IP/MPLS and SR networks. This includes slice controller interfaces and the mapping to external slice definitions (e.g., 3GPP 5G).
6. Power-aware traffic engineering: architecture, path placement strategies, and signaling mechanisms to allow TE networks to reduce or manage power consumption.
7. Multipath traffic engineering (MPTE): if consensus is reached, specification of the architecture, RSVP-TE signaling, and YANG data model for establishing and managing TE DAGs (Directed Acyclic Graphs) and Junctions.
8. If consensus is reached, gap analysis of TE-related QoS and service-assurance requirements of emerging use cases; any resulting protocol work is carried out in the WG that owns the protocol.

Requirements may be documented in stand-alone RFCs, may be folded into architecture or solutions RFCs, may be recorded on a wiki, or may be documented in an Internet-Draft that is not progressed to RFC.

The TEAS WG will coordinate with the following working groups:

- With the MPLS WG to maintain and extend MPLS-TE protocol mechanisms and to determine whether they should be generalized.
- With the CCAMP WG to maintain and extend non-packet, data-plane technology-specific TE protocol mechanisms and to determine whether they should be generalized.
- With the LSR (OSPF and ISIS) WG to maintain or extend TE routing mechanisms.
- With the PCE WG on uses of a PCE in the traffic-engineering architecture, on PCE extensions per the above, and on RSVP-TE extensions to support PCE WG identified requirements.
- With the IDR WG on the use of BGP-LS in TE environments.
- With the DetNet WG on mechanisms (YANG models and protocols) to support DetNets.
- With the SPRING WG on TE architecture and, where appropriate, TE-related protocol extensions.
- With the 6MAN and SRv6OPS WGs on TE specific IPv6 and SRv6 aspects.
- With the ONSEN WG on service and network abstraction models. YANG models already adopted by TEAS (including the network slice and ACTN models) remain in TEAS, and TEAS will route future service/network abstraction-layer modeling that is not TE-specific to ONSEN.
- With the NMOP WG on TE specific operational network management issues, telemetry, and network topology modeling efforts.
- With the GREEN WG and other energy-related efforts on power and energy metrics.
- With the TSVWG on QoS-related mechanisms.

In doing this work, the WG will cooperate with external SDOs (such as the ITU-T, the IEEE 802.1, 3GPP and the O-RAN Alliance) as necessary.
