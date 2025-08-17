IETF 124 Montréal TIPTOP/Deepspace Hackathon Experiment

Space communications have large delays (2 secs one-way delay to Moon, 4-22 mins to Mars) and intermittence (because relay orbiters going on the other side of the celestial body). The key adaptations to make to the IP stacks are (briefly, see drafts for details) - for forwarders facing intermittence, store temporarily packets instead of dropping them, when a link goes down - adjust transport and application timers. The [TIPTOP](https://datatracker.ietf.org/group/tiptop/about/) working group is making group progress on specifications. The purpose of this experiment is to start trying early implementations and get experience on using applications in this environment.

** Experiment Information

We will be broadcasting two SSID on the hackathon wireless network: ietf-moon which will inject a 2 seconds one-way delay and ietf-mars which will inject a 4 minutes delay. Both will also see intermittence.

More details to follow 
