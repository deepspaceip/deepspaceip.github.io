# DEEPSPACE BOF proposal

Deep space communications involve long delays (e.g., Earth to Mars is 4-20 minutes one-way) and intermittent communications, because of orbital dynamics. The combination of long delays and intermittent communications makes the round-trip time very large and very variable. Multiple space agencies and private sector companies are planning to deploy distant IP networks such as at Earth's Moon and Mars, including on their surfaces, orbiting, or in other vicinity such as Lagrange points and transfer trajectories. By having the deep space links also carry IP, it makes a complete end to end IP network. However, given the delays and disruptions, the upper layers such as transport and application protocols have to be specially configured to support this environment. While "deep space" is technically defined by ITU as starting at 2M km away from Earth, therefore excluding Earth's Moon, this IETF work encompasses a wide range of delays that is relevant for lunar and other "near space" use cases (e.g. lagrange points, etc.) falling between typical terrestrial Internet and deep space latencies.

IP is specified in the LunaNet Interoperability Specification (LNIS) being used in NASA, ESA, and JAXA lunar relay satellite projects, and IP is included in the International Communication System Interoperability Standards (ICSIS) for Lunar Gateway mission users.  The systems developed and tested at the Moon are planned to be extended for later Mars exploration.  IP is already applicable in local networks on the lunar and Martian surface between vehicles, and within habitats or space stations, but can also be used on direct-with-Earth (DWE) links, and for relaying between proximity and DWE trunk links. IETF guidance on the configuration of IP applications and network services for such uses will directly benefit the growth and interconnection of lunar and Mars networks being built and operated by diverse parties.

## Required Details
* Status: WG Forming
* Responsible AD: Eric Vyncke
* BOF proponents: Marc Blanchet <marc.blanchet@viagenie.ca>, Wesley Eddy <wes@mti-systems.com>, Tony Li <tony.li@tony.li>
* BOF chairs: TBD
* Number of people expected to attend: 100
* Length of session (1 or 2 hours): 2 hours
* Chair Conflicts: TBD
* Technology Overlap: dtn, quic, tvr, intarea, tsvwg
* Key Participant Conflict: dtn, quic, tvr
* Scheduling: given expected remote participation from North America and Asia, prefer afternoon session

## Information for IAB/IESG
Since IETF117, this group met at each IETF and discussed using the deepspace@ietf.org mailing list. A web site (https://deepspaceip.github.io) archives all presentations and documents.
During IETF120 and subsequently on the dtn and deepspace mailing lists, there was a proposal to integrate this work (deep space IP) into the dtn working group through a recharter. The conclusion was that it would be better to have a separate working group. 

The dtn working group is working on similar use cases but using the Bundle Protocol(BP) stack. Since the publication of RFC4838 which initiated the work on BP, the IP and associated transport stack has evolved to support disconnected devices like IoTs and new transport protocols such as QUIC. This makes a different situation than 25 years ago, and makes IP usable in deep space.

## Agenda
* Problem Space,TBD 
* LunaNet: Context and Interoperability Specification related to IP, Wesley Eddy
* Moon Mobile Provider Requirements, KDDI
* China Space Agency Plans for IP in Deep Space, Xiongwen He
* Architecture, Marc Blanchet
* Proposed Charter, BOF co-chairs
* Next Steps, BOF co-chairs

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
