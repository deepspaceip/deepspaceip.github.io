# IETF-118 Deep Space IP Meeting Minutes
- see [agenda](README.md)
- warning: not comprehensive/verbatim
- unfortunately, there is no recording of the meetings
- thanks to note takers (for meeting 2): Émile Stephan, Joerg Deutschmann

## Side Meeting 1
- Tuesday Nov 7th, 18h00-18h30 (Prague Timezone), local room: Karlin 4
- ~50 attendees

### [Administrativia](ietf118-deepspace-blanchet.pdf.pdf), Marc Blanchet
- meeting under IETF Note Well
- group mailing list: [deepspace@ietf.org](https://www.ietf.org/mailman/listinfo/deepspace)
- group web site: [https://deepspaceip.github.io](https://deepspaceip.github.io)

### [Proposed Architecture in One Slide](ietf118-deepspace-blanchet-in-one-slide.pdf), Marc Blanchet
  - Laurent Toutain: what kind of bandwidth? Marc: from bits/sec to gigabits/sec
  
### [QUIC for deep space](ietf118-deepspace-quic-in-space.pdf), Christian Huitema
  - Gorry Fairhust: do we really need congestion control at all for these links (since they may be dedicated)? Marc: currently, deep space links are dedicated to specific missions by time slots but not necessarily in the future. Christian: needed not only for congestion issues. 


## Side Meeting 2
- Thursday Nov 9th, 18h00-19h00 (Prague Timezone), local room: Karlin 4
- ~40 attendees
- Admin
   - Good expertise in the room. Please provide constructive comments.
   - No time for all presentations.
   - QUIC experts are still in MOQ WG session, will join after 30mn.
 
### [IP forwarding in deep space](ietf118-deepspace-forwarding-dionne.pdf), Jean-Philippe Dionne
- previously worked on Bundle Protocol
- implementation in Linux Kernel
- tc qdisc "plug" intended to store VMs
- what and how is the limit of packets stored in the queue?
- looked into tun, depends on user vs. kernel space
- Looking forwarding store and forward (saf) in linux kernel.
- long delay and inter links, need to store instead of drop.
- Want to avoid retransmission.
- 2nd method more flex: packets go to u space when congestion or disruption
- ebpf dpdk not studied
- implementation in Go and C using netns and containers. Next to be more realistic
- 1st method is one queue but 2nd allow queue management
- Chat about storing many PDUs, point to DTN WG

### [DNS in Mostly Isolated Networks](ietf118-deepspace-dns-isolated-networks.pdf), Marc Blanchet
- draft-many-dnsop-dns-isolated-networks
- Marc presented it a DNSops get DNS local resolutions; wanted DNSSEC and remote management.
- The draft is not fully detailed yet.
- 3 approaches:
   - 1st pre-walk of all known names; save what Keith Scott find; need to know all the names
   - 2nd relies on knowledge and access of the needed hierarchy; upload and serve these zone; risk to got huge nb of useless names (aka .com 😊)
   - 3rd is to create a special version of the zone with only names needed; sign the zone and upload
- Other : a new root, split DNS
- Unsure that the best approach is known yet
- not designed for internet;
- details context, infrastructure, approaches as in slides
- TTL considerations for names with shorter lifetime?
- must be long enough for RR, cf. DNSSEC, local resolver
 
### [CoAP in space](ietf118-deepspace-coap-in-space.pdf), Carlos Gomez Montenegro
- COAP is worth considering,
- Recall of COAP genesis. It a rest protocol for IoT env constraint nodes : energy, infrequently connected;
- Summary: 4 bytes headers, offer flexibility also asynchronous messages, proxy and cache, stateless mapping to HTTP
- Detail: initially for UDP, ARQ and CC : partially reliable; support large payload block wise transport
- Sec: several options: DTLS, e2e sec with OSCORE;
- Draft under prep for space mapping.
- Chat: CoAP over Bundle, CoAP over HTTP over Bundle? Issue with CoAP over Bundle?
 
### [QUIC over TAPS API for Deep Space: TAPSce And Careful Resume (CR), and BDP frame](ietf118-deepspace-taps-careful-resume.pdf), Emile Stephan
- report from QUIC over TAPSce (pronounce it TAPsee 😊) Hackathon, cf. Careful Resume and BDP Frame
- Max worked on python-asyncio-taps and aioquic
- reference to Careful Resume done in Hackathon
- future plans: interop, feedback from DTN
- TAPSce members and fans
- Careful Resume slide
- QUIC BDP Frame Extension slide
- BDP Frame was planed to be presented in QUIC working group at IETF118 but run out of time
- comment from Raffaello Secchi: CUBIC has HyStart, Careful Resume
starts at data rate which has previously been used, originally planed as
replacement for TCP PEPs (large round trips)
- but must be powered on both sites?
- Careful Resume can be used after idle times
Raffaelo detailed the Careful Resume usage.
 
 
### [Extensions for QUIC in Deep Space](ietf118-deepspace-quic-extensions.pdf), Francois Michel, Maxime Piraux
- draft-michel-quic-fec
- draft-piraux-quic-additional-addresses
- based on what Christian Huitema has presented
- loss recovery -> use FEC
- Francois presents FEC
   - part of this thesis (URL given in slides)
   - 1000 Exp images with RTP in QUIC  using SSIM score over starlink
   - 3 imple QUIRL QUIC RTP: the smaller the best
- Can be applicable to deepspace using Christian
- implemented in quiche using QUIRL for FFmpeg/GStreamer and RTP packets
- use case: replaying drone videos over Starlink
- comment from Maxime: improve RTT by reliability
- Maxime presents additional addresses
  - missing block: announce additonal addresses (was removed from
multipath draft)
  - deep space devices probably multihomed
 
### Next steps
- virtual interim meeting in maybe January? Positive feedback from the room.
- focus on QUIC over long delay links, storing IP packets
 
### Chat log for meeting 2

Keith Scott • What's the limit on the number of packets linux will store in the interface queue?
Can Keith Scott reach into the stored packets and delete ones that may no longer be viable?
OK, with the TUN method, sure Keith Scott can get at the packets, just hard to do if they're in the interface queue

Jorge Amodio • not good

Keith Scott • OK, I'm just thinking, Keith Scott're going to want to be able to store about 1 BDP to mars @ 40min RTT

Tony Li • I agree. But bw is small, so this might be viable with an SSD.

Jorge Amodio • rad tolerant memory ain't cheap

Tony Li • The memory requirements shouldn't be protocol specific. IP or BP should be the same.

Jorge Amodio • sure but BP already took care of all these
messing with the kernel in deep space... hhhmmm not good

Keith Scott • Overall memory requirement is probably the same, but it's a bear to reach into the kernel and rearrange its sk_buffs

Tony Li • Another reason why the tunnel device would be cleaner.

Dan York • For whomever is in the room operating as the host, Christian Huitema is in the waiting room seeking to be let in.

Jorge Amodio • They are not similar

Dan York • From Alex Petrescu on the email list - there are now 5 people waiting in the virtual lobby.

Keith Scott • So is the proposal / thought to run QUIC as the transport layer over end-to-end IPv6?

Jorge Amodio • DTN is an architecture not a feature set

Keith Scott • So think of this as the question: can we implement the DTN architecture using IPv6 packets as the network-layer framing structure and QUIC for transport-layer features.

Jorge Amodio • QUIC sounds good as a CL

Keith Scott • Could be.
What if the coherence time of the channel characteristis (RTT, bandwidth) is less than the RTT?  The values careful resume is going to use to restart the link will be out-of-date, no?

So if I don't use careful resume, do I go back to some sort of bandwidth probing?

Jorge Amodio • All these feel more like a hack than a thoughtful architecture

Tony Li • IPv4 might be more appropriate, given the lack of bandwidth.

Jorge Amodio • No IP is even better 🙂

Keith Scott • How do Keith Scott resolve the following:
1) When sending across the Internet, Keith Scott must use an accepted congestion control mechanism.
2) When sending to a remote host (e.g. a Mars rover) the source may need to send all the information without hearing ANYTHING back from the receiver (because e.g. there's no off-earth link when the sender starts to send).  I say that Keith Scott may need to send all the infomation because Keith Scott need to get the information queueud up at the head-end of the next-to-become-available link so that Keith Scott can make efficient use of that link.
3) The next-to-become available link may have completely different channel characteristics (ok, mostly bandwidth) than the previousl head-end for storage (e.g. last time Keith Scott sent from a 70m dish at Goldstone to Mars Odyssey, this time via a 34m dish to MRO).

Tony Li • Using a proxy which has terrestrial settings on one side and deep space on the other might solve 1.

