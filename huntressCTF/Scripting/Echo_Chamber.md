### Challenge description

Is anyone there? Is anyone there? I'm sending myself the flag! I'm sending myself the flag! 

### Solution

Pcap file with bunch of `icmp` packets, hmm.. we get the data and decode in CyberChef.
```
tshark -r echo_chamber.pcap -Y "icmp.type==8" -T fields -e data | cut -c 1-2 > flag.txt
```
import to CyberChef and pick `From hex` and `Render image`. You get a png with the flag.

flag{6b38aa917a754d8bf384dc73fde633ad}