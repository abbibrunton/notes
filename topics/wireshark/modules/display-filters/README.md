# Display Filters
<!--TOC_START-->
### Contents
- [Overview](#overview)
- [Filtering by Protocol](#filtering-by-protocol)

<!--TOC_END-->
## Overview
Wireshark's display filter is a bar located at the top, just above where the packets are being shown.
This is where you type expressions to filter the frames, IP packets, or TCP segments.

The screenshot below shows the display filter being used to only show packets using TCP:

![Wireshark Display Filter](https://lh3.googleusercontent.com/VtovFjwfL1fIKWCN8cZ1D_D_gM0sRlACU-Tj0aOGRDkuVj1MFb7fw5oS4qLkcWMXNwDvFumS546eKLJqwMGztwep24tC-DQKgp13lLVO1SRSATgNERooMwBDqc4d6E3GmLFkg56HekgIiAaFp46KUfhNMlHMm8r0zfqYlHmgzj9F5Lu0LMD8Umk_MKZrDW-n0GGVBQabe4pEx0nO2OBXbJxCzJqWzUd9f9czTTWNacs2XTj2nl3kQdMxmFyM4GJoZNAORRyj60PwT83RGyprUwDNnlTXGojOqsrMzktKbUCIpIre4nSZN8vwl_kfKr69p-GDO-DBt9dMHZh7dw2gg2hH8eqOZA5FPs1bwTcJJySrBRzWmFV1u6DW1RySHfFFglno2r3wzWMeyrG0rMLZBYDZiBNfvlMOOTLG_jK8WZ-fyFBQ367oUerKerL6GKwSWvP86VfA1YhZNwrjSQvIxmJAZCbeFpU5A0LJkyNnolOashFVHqIktURpgc2ZkeyJa_hjFvN3qzJ6upw9f7pi-TTnoIhT6BP8W70LpGHuxxb_NncEQj6_sHm0Ksfnv14hz5yraDRKliSTzx87l4izwMSL45neSozGzpR_8feTc3ouSTyoS5hoE1lRLLg4UEmtbvlkWOC_oN2qQLs-QGgWCVu52jcyBEsUtVCFUHKOC7QxGm2227d1uHG0XjIYLITYd_sIgDAUo3oG7lskrtL06Xcchpjf31N4Hovmo3Z0inFOBThP=w1168-h404-no)

## Filtering by Protocol
To only show a certain protocol acronym can usually just be put in the display filter.
It's important to keep the letters lowercase however:

| Protocol | Display Filter Value |
|----------|:--------------------:|
| Transmission Control Protocol (TCP) | tcp |
| User Datagram Protocol (UDP) | udp |
| Internet Control Message Protocol (ICMP) | icmp |
| Server Message Block (SMB) | smb |
