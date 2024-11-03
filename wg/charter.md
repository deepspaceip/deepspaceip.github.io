# DEEPSPACE WG

Some space communications involve long, variable delays (e.g., Earth to Mars is 4-20 minutes one-way) and intermittent end-to-end connectivity due to orbital dynamics. Until now, space communications have relied on layer-2 point-to-point networking, sometimes involving relays, without establishing an end-to-end layer-3 network.

Today, space agencies and the private sector are planning to deploy IP networks on the surfaces of celestial bodies, such as the Moon or Mars, that connect to orbital equipment and further on to Earth, establishing a complete end-to-end IP network across space.

However, given the delays and disruptions involved in space communications, protocols may have to be profiled to operate efficiently in this environment. 

This working group will work on the following items:

* Documenting the key characteristics that make the space environment unique and considerations for properly designing space applications will be provided.

* Work on an architecture for using the IP stack in space that discusses the key differences to terrestrial IP use. While lunar networking is the first deployment of this work, the overall architecture should support communication with Mars and, ideally, further out.

* A profile for the QUIC transport protocol that enables efficient end-to-end use of QUIC in space. Given that TLS is an integral component of QUIC, considerations for the use of TLS are also in scope.

* Considerations for the deployment of DNS will be documented, given the often disconnected nature of space networks.

Other topics, including the Bundle Protocol (BP), are out of scope for this WG.

The DEEPSPACE WG should avoid modifications to existing protocols. Wherever possible, existing protocols must be used within existing architectures to implement the necessary functions. Any modifications of existing protocols should be carried out in the WGs responsible for them and in coordination with the DEEPSPACE WG. Alternatively, after agreement among all the relevant WG chairs and responsible Area Directors, the work may be done in the DEEPSPACE WG.

The working group will welcome discussions with key stakeholders, such as the working groups of the LunaNet Interoperability Specification (LNIS), the Interagency Operations Advisory Group (IOAG), the Consultative Committee for Space Data Systems (CCSDS), space agencies, and the private sector. Within the IETF, it will coordinate its work with TVR on scheduling, QUIC on profiling, TLS on security, DNSOP, and DTN on interworking.
