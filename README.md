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

[charter-ietf-teas-03.md](./charter-ietf-teas-03.md)

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
