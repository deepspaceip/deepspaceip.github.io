# Taking IP To Other Planets (TIPTOP) WG Charter
Space communications involve long, variable delays (e.g., Earth to Mars is 4-20 minutes one-way) and intermittent end-to-end connectivity due to orbital dynamics. Until now, space communications have relied on layer-2 point-to-point networking, sometimes involving relays, without establishing an end-to-end layer-3 network.

Deploying IP networks on the surfaces of celestial bodies, such as the Moon or Mars, that connect to orbital equipment and further on to Earth creates the opportunity for in-space IP-based internetworking between organizations and the ability to support IP applications end-to-end.

Given the delays and disruptions involved in space communications, protocols may have to be profiled or extended to operate efficiently in this environment. While lunar networking is the first planned deployment of this work, designs should consider support for communication with Mars and other deep space targets.

This working group will work on the following items:

* Description of the key characteristics, use cases, and requirements that make the space environment unique. 
* Documentation of the necessary differences that apply to the IP architecture when considering space networking compared to terrestrial IP use. 
* A profile for transport protocols, starting with QUIC, that enables efficient and secure end-to-end use in space.
* Considerations for the deployment of DNS will be documented, given the often disconnected nature of space networks.

The Bundle Protocol (BP) and the operation of LEO, MEO, and GEO constellations are out of scope for this WG.

The TIPTOP WG should avoid modifications to existing protocols. Existing protocols must be used within their deployment envelopes to implement the necessary functions wherever possible. Any modifications of existing protocols should be carried out in the WGs responsible for them and in coordination with the TIPTOP WG. Alternatively, after agreement among the relevant WG chairs and Area Directors, such work may be done in the TIPTOP WG.

The working group welcomes discussions with key stakeholders, such as the working groups of the LunaNet Interoperability Specification (LNIS), the Interagency Operations Advisory Group (IOAG), the Consultative Committee for Space Data Systems (CCSDS), space agencies, and the private sector. Within the IETF, it will coordinate its work with TVR on scheduling, QUIC on profiling, TLS on security, DNSOP, and DTN.

## Work Items

* Key characteristics, use cases, and requirements, Informational
* Applicability of the IP Architecture to space networking, Informational
* QUIC profile space networking, Informational
* DNS considerations in space networks, Informational
