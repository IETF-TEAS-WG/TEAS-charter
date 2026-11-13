# TEAS WG Charter — Proposed Update (working draft)

Basis: current charter text (as pasted), the 26 active WG drafts and 35 published RFCs on the datatracker, and the IETF 127 agenda (MPTE, RSVP-TE/SRv6, RSVP resource notifications, power transition, distributed bandwidth management, 6G QoS gap analysis).

## 1. Where the charter is out of date

| Area | Charter today | Reality |
|---|---|---|
| **Network slicing** | Not mentioned | Biggest body of WG work. Published: RFC 9543 (framework), RFC 9732 (NRP-based enhanced VPN), RFC 9889 (5G slices over IP/MPLS). Active: ns-ip-mpls, nrp-scalability, nrp-yang, composite-network-slices, ietf-network-slice-nbi-yang, network-slice-topology-yang, ns-controller-models, ns-models-applicability, 5g-network-slice-application, applicability-actn-slicing |
| **ACTN** | Only a passing mention in the intro | Published: RFC 8453, 8454, 9731 (VN YANG). Active: POI applicability and assurance, PM telemetry/autonomics, plus the inter-operator extension individual draft |
| **Deliverables list** | Six items, mostly done: delay/jitter metrics, E-NNI, associated LSPs (RFC 7551), protection, abstraction and distribution of TE information (RFC 7926) | Needs replacing with current work. Closed items should move to "completed" or be removed |
| **YANG** | Item 6 is generic | Active: te, te-mpls-topology, l3-te-topo, te-topology-profiles, topology-filter, te-service-mapping, yang-rsvp, yang-path-computation, rfc8776-update. The charter should name this as an explicit deliverable |
| **RSVP-TE** | (d) covers generic extensions only | Active: in-place LSP bandwidth update, HMAC-SHA2 and auth-v2. Security of the signaling protocol itself is not covered by (f), which is about "management and security techniques for TE path and tunnel control" |
| **Power / energy** | Not mentioned | draft-ietf-teas-power-steering is a WG draft. draft-many-teas-rsvp-power (power transition for TE resources) is an individual draft |
| **New TE mechanisms** | Not mentioned | MPTE (multipath TE, with RSVP signaling and a YANG data model), RSVP-TE on an SRv6 forwarding plane, RSVP resource notifications, and distributed bandwidth management |
| **MIB** | (f) says "YANG and MIB modules may be considered" | MIBs are obsolete. Drop the reference |
| **Forwarding planes** | Wording is MPLS and GMPLS centric ("IP, MPLS and GMPLS") | SR (SR-MPLS and SRv6) and "other mechanisms" need to be explicit |
| **Coordination list** | SFC, SPRING, etc. | See section 4 |
| **Intro paragraph** | Describes TE as MPLS TE plus GMPLS | Should mention slicing, SR and SRv6, and energy as drivers |

## 2. What is missing: proposed new charter items

1. **Network slicing**
   - Architecture, realization and scalability of IETF Network Slices and NRPs (RFC 9543 follow-ons).
   - Related YANG models, controller models and applicability documents.
   - Mapping to external slice definitions (e.g., 3GPP).
2. **Power-aware TE**
   - Architecture, metrics and path-placement strategies for reducing power consumption.
   - Signaling of power-state transitions of TE resources (RSVP-TE).
   - Coordination on energy-related YANG and metrics with other WGs.
3. **Multipath TE (MPTE) and new TE signaling**
   - Evaluate and, if consensus exists, specify architecture, RSVP-TE signaling and YANG for multipath TE.
   - RSVP-TE signaling over SRv6.
   - RSVP-TE resource notifications.
   - Distributed bandwidth management.
4. **RSVP-TE hardening and maintenance**
   - Cryptographic authentication and in-place updates.
   - Scalability.
   - Coexistence with SR.
5. **ACTN and controller-based TE**
   - Continue ACTN applicability work (POI, assurance, slicing).
   - Telemetry-driven operation.
   - Inter-operator coordination if adopted.
6. **TE-related QoS and service assurance**
   - Option to cover per-flow and fine-grained QoS requirements for emerging services (e.g., 6G) as gap analysis only.
   - Any solution work is done in coordination with the owning WGs.

## 3. Proposed revised charter text

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

## 4. Coordination list changes

Checked on the datatracker (12 Nov 2026):

- **SFC:** concluded (July 2023). Dropped from the text above.
- **SRv6OPS, GREEN, TSVWG:** all active. GREEN is chartered ("Getting Ready for Energy-Efficient Networking"), so the "(if chartered)" qualifier in the text can be dropped.
- **NMOP:** active, and a recharter is in progress (proposed charter 01-02, updated 2026-11-05). It covers operator-driven network management issues, telemetry and short-term experiments. It may standardize YANG models for operational issues. Per ONSEN's charter, topology-related efforts stay in NMOP.
- **ONSEN:** active (Operationalizing Network & SErvice abstractioNs, charter v01). It is the focal point for service and network abstraction modeling. Its charter lists Network Slicing, Virtual Network (VN) and ACTN among the YANG models to be assessed and updated, alongside the VPN, attachment circuit and SAP models.
- **ONSEN's stated relationship with TEAS:** network or service-level modeling already adopted by BESS, CCAMP or TEAS stays there, but ONSEN takes future network and service data-modeling efforts from these WGs. That affects deliverables 1, 2 and 5 above.
- **Added to the coordination list:** ONSEN, NMOP, SRv6 (6MAN, SRv6OPS), GREEN, TSVWG, and 3GPP and O-RAN as external bodies. OPSAWG is replaced by ONSEN and NMOP. I haven't checked the current MPLS or CCAMP status.

## 5. Open points for you and the chairs

1. **MPTE scope.** Item 7 is conditioned on WG consensus ("if consensus is reached"). This is the usual charter convention for work that isn't yet adopted, and it matches how the WG will treat the drafts anyway.
2. **6G QoS.** Included as "gap analysis" only. Drop item 8 if the chairs don't want to signal that scope yet.
3. **Individual drafts.** The charter names themes, not individual drafts. Deliverable 4 now reads generally ("scalability, security, and extensions to realize distributed bandwidth management over different forwarding planes"), so check that RSVP resource notifications and RSVP-TE over SRv6 are still clearly in scope once adopted. Deliverable (d) covers new forwarding planes in general.
4. **Milestones.** The datatracker milestones page also needs a refresh once the text is agreed. I did not review the current milestones.
5. **Closed work.** Do you want an explicit "completed work" list, or remove the old items? I merged them into item 3.
6. **Overlap with ONSEN.** ONSEN's charter lists network slicing, VN and ACTN models among those it will update, and says it will take future service/network modeling from TEAS. Decide how to position deliverables 1, 2 and 5. The text above keeps TEAS ownership of already-adopted work and of TE-specific models, and names ONSEN in the coordination list. The chairs and AD may prefer a firmer boundary (e.g., TEAS owns TE-specific and slice-realization models, ONSEN owns generic service abstraction models), and ONSEN's own charter text may need a matching tweak.
7. **Overlap with NMOP.** TE topology YANG (te-topology, l3-te-topo, topology-filter, te-topology-profiles) is a topology effort. ONSEN's charter keeps topology work in NMOP, so be explicit that TE topology models stay in TEAS to avoid confusion.
8. **Wording check.** The text should be checked against the datatracker's current charter, since I worked from the version you pasted.
