# Deep Space IP Testbed

This section describes the testbed used for simulation as well as results.


## Description
The testbed uses various tools such as:

- [tc netem](https://man7.org/linux/man-pages/man8/tc-netem.8.html) which provides tooling to simulate network conditions such as delay, duplicate and reordering. However, to simulate larger than 274s delays, one has to use a updated version, as the [patch](https://git.kernel.org/pub/scm/network/iproute2/iproute2.git/commit/?id=9a6b231ea1b09e450688c5814a4c89a57cdbee77) to support 2^64 seconds delay was added to the git in March 2024 .
- [QUINN](https://github.com/quinn-rs/quinn) QUIC stack, which provides an API to set various transport configuration parameters.
- [multipass](https://multipass.run) which creates on the fly instances of Ubuntu images.
- [cloudinit](https://cloudinit.readthedocs.io/en/latest/) which configures the ubuntu images to be ready for simulation
- various tools: docker, tcpdump, wireshark, ...

## Results

- [HTTP Request to Voyager!](http-voyager.pdf)
- [HTTP with 10 days RTT](http-10daysRTT.pdf)
- [IP packet storage under link interruption](ip-storage-link-interruption.pdf)
- [SNMP](snmp.pdf)
- [NTP](ntp.pdf)