## Gossip-Style Failure Detection Service Simulation: CSC501 Fall 2015

Authors:
- David Joshua Zager (@djzager)
- Sarthak Kukreti (@skukreti)
- Vipin Sharma (@muzzycoder)

Running instructions:

1. Use make to build executable
```
   $ make clean
   $ make a4
```

2. Run program N times (on same machine or multiple machines) as:
```
      $ ./p4 N b c F B P S T
```

   where:
       N Number of peer nodes
       b gossip parameter
       c gossip parameter
       F number of seconds after which a node is considered dead
       B number of bad nodes that should fail
       P number of seconds to wait between failures
       S the see of the random number generator
       T the total number of seconds to run

**Caveat:** 

- The simulation program does not cover discovery. Each instance **assumes** a shared filesystem (eg. AFS) across all nodes and writes it's IP address and ports to a common file. 
- Additionally, the simulation program uses clever random number seeding across different machines to kill off **exactly one node** every P seconds.
