# Deepspace BOF proposal

Deep space communications involve long delays (e.g., Earth to Mars is 4-20 minutes) and intermittent communications, because of orbital dynamics. The combination of long delays and intermittent communications makes the round-trip time very large and very variable. Space agencies and private sector are planning to deploy IP networks on celestial bodies, such as Moon or Mars, ground, orbits and vicinity. By having the deep space links also IP, it makes a complete end to end IP network. However, given the delays and disruptions, the upper layers such as transport and application protocols have to be profiled to support this environment.

## Required Details
* Status: WG Forming
* Responsible AD: Eric Vyncke
* BOF proponents: TBD 
* BOF chairs: TBD
* Number of people expected to attend: 100
* Length of session (1 or 2 hours): 2 hours
* Chair Conflicts: TBD
* Technology Overlap: dtn, quic
* Key Participant Conflict: dtn, quic

## Information for IAB/IESG
During IETF120 and subsequently on the mailing list, there was a proposal to integrate this work (deep space IP) into the dtn working group through a recharter. The concensus and conclusion is that it would be better to have a separate working group. 

The dtn working group is working on the same use case but using the Bundle Protocol(BP) stack. Since the publication of RFC4838 which initiated the work on BP, the IP stack has evolved to support disconnected devices like IoTs and new transport protocols such as QUIC. This makes a different situation than 25 years ago, and makes IP usable in deep space. 

## Agenda
* Problem space and architecture
* Proposed charter
* Next Steps

## Links
* Mailing List: https://www.ietf.org/mailman/listinfo/deepspace
* Draft charter: https://deepspaceip.github.io/wg/charter.md
* Relevant Internet-Drafts:
  * [draft-many-deepspace-ip-assessment](https://datatracker.ietf.org/doc/draft-many-deepspace-ip-assessment/) 
  * [draft-huitema-quic-in-space](https://datatracker.ietf.org/doc/draft-huitema-quic-in-space/)
  * [draft-blanchet-dns-isolated-networks](https://datatracker.ietf.org/doc/draft-blanchet-dns-isolated-networks)
  * [draft-gomez-core-coap-space] (https://datatracker.ietf.org/doc/draft-gomez-core-coap-space/)
