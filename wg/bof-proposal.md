# Deepspace BOF proposal

Deep space communications involve long delays (e.g., Earth to Mars is 4-20 minutes) and intermittent communications, because of orbital dynamics. The combination of long delays and intermittent communications makes the round-trip time very large and very variable. Space agencies and private sector are planning to deploy IP networks on celestial bodies, such as Moon or Mars, ground, orbits and vicinity. By having the deep space links also IP, it makes a complete end to end IP network. However, given the delays and disruptions, the upper layers such as transport and application protocols have to be profiled to support this environment. 

IP is specified in the current set of lunar relay procurements from US, European, and Japanese space agencies that reference the LunaNet Interoperability Specification(LNIS). IP is also mentioned in the International Communication System Interoperability Standards (ICSIS) for Lunar Gateway mission users. LNIS indicates IP for realtime network data services, and it is applicable not only within the "island" of lunar surface vicinity, but also for direct-with-Earth (DWE) links, and for relaying between proximity and DWE trunk links. The LNIS work is looking to get proper advice from IETF on how to configure IP applications and network services. 

## Required Details
* Status: WG Forming
* Responsible AD: Eric Vyncke
* BOF proponents: Marc Blanchet <marc.blanchet@viagenie.ca>, Wesley Eddy <wes@mti-systems.com>, Tony Li <tony.li@tony.li>
* BOF chairs: Lars Eggert, Alvaro Retana
* Number of people expected to attend: 100
* Length of session (1 or 2 hours): 2 hours
* Chair Conflicts: TBD
* Technology Overlap: dtn, quic
* Key Participant Conflict: dtn, quic

## Information for IAB/IESG
During IETF120 and subsequently on the dtn and deepspace mailing lists, there was a proposal to integrate this work (deep space IP) into the dtn working group through a recharter. The concensus and conclusion is that it is not appropriate to integrate the two and would be better to have a separate working group. 

The dtn working group is working on the same use case but using the Bundle Protocol(BP) stack. Since the publication of RFC4838 which initiated the work on BP, the IP stack has evolved to support disconnected devices like IoTs and new transport protocols such as QUIC. This makes a different situation than 25 years ago, and makes IP usable in deep space.

## Agenda
* Problem Space
* LunaNet: Context and Interoperability Specification
* Architecture
* Proposed Charter
* Next Steps

## Links
* Mailing List: https://www.ietf.org/mailman/listinfo/deepspace
* Draft charter: https://deepspaceip.github.io/wg/charter
* Relevant Internet-Drafts:
  * [draft-many-deepspace-ip-assessment](https://datatracker.ietf.org/doc/draft-many-deepspace-ip-assessment/) 
  * [draft-huitema-quic-in-space](https://datatracker.ietf.org/doc/draft-huitema-quic-in-space/)
  * [draft-blanchet-dns-isolated-networks](https://datatracker.ietf.org/doc/draft-blanchet-dns-isolated-networks)
  * [draft-gomez-core-coap-space] (https://datatracker.ietf.org/doc/draft-gomez-core-coap-space/)
* Relevant Documents:
  * [LunaNet Interoperability Specification](https://www.nasa.gov/directorates/somd/space-communications-navigation-program/lunanet-interoperability-specification/)
  * [The Future Lunar Communications Architecture, Interagency Operations Advisory Group](https://www.ioag.org/Public%20Documents/Lunar%20communications%20architecture%20study%20report%20FINAL%20v1.3.pdf)
  * [The Future Mars Communications Architecture, Interagency Operations Advisory Group](https://www.ioag.org/Public%20Documents/MBC%20architecture%20report%20final%20version%20PDF.pdf)
