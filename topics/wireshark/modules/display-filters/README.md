# Display Filters
<!--TOC_START-->
### Contents
- [Overview](#overview)
- [Filtering by Protocol](#filtering-by-protocol)
- [Relational Operators](#relational-operators)

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
| Transmission Control Protocol (TCP) | `tcp` |
| User Datagram Protocol (UDP) | `udp` |
| Internet Control Message Protocol (ICMP) | `icmp` |
| Server Message Block (SMB) | `smb` |

Here's an example for filtering out packets using the ICMP protocol while a `ping` command to `google.com` was being run:

![ICMP Display Filter](https://lh3.googleusercontent.com/U2zRdDiNO2U4i_ToQbjnaz6dONiqcPzH-SZLKm4lmvAuq02FGAYvL6yNHg2h08tp1gWWbhx1gsdIpl8QIo2OfMGet-YCRGu2Cb0Fep1BqKguzJnvHZL5oCm4RgeaiX_BrvCA308bNrfH9sbGq0KJR85jYTV_aNfMCLC6acSjq8XWUoJoWD3MXBEPChuuFXoj7tLny1qXz-ELT-w0jT6Rw7KBur1quMtxClg69d0VFfy-M0Eyncum08vYTNJhe-MXwWQ2vdx1jQj7tCrodoEGjNNISTfBD2WR-W3xsSrMvLaqXSL6Hs6XoYAiaPeQqT3_lW1Qk7JmYC6NlquJ6SUpASjeqynax5gcdnmPYGk_IprNRKCKcHkF_VbhK0YnCEjW1w3nH1C_UgYGfLlcfzYA5_6ks9oBm2OOPr21vLYaXeXSgZWXHrLppRNyDxRfRwW7chXvNFizuh79ilL2NbZtqPeen1RRvWtuoXonpSsiwMzijzonPrLhy90By0nwipxiw5z-5XlTOB_spZNfNyI8OoBv87ctqI03h5vmwFC7wS72RWhfHUK8XpJBOHAGdYVRf12BctgIxjp8mafb1ZYiLmntgGCIHQCozO88FBcx3-N-pU9s72xOQvaJW1OhNhRZlRIZpEOCiMakx18xS-HUOOngueoYFcxHvYADed6-ULgn0cGK-oNAFmArMPxf_5ar7d97xX2NE-GYaF4Wj1OduOxbjsNrAYQDCHKDsCG-Dnghxhag=w1168-h593-no)

## Relational Operators
The operators here have the same logic as most programming language.
When the condition that you put into the display filter equates to true, the packet will be shown.
| Operator | Description |
|----------|-------------|
| `==`     | Checks if the values of two operands are equal or not, if yes then condition becomes true. An example of this would be checking if the packet is from a certain host: `ip.host == example.com` |
| `!=`     | Checks if the values of two operands are equal or not, if values are not equal then condition becomes true. You could use this to show packets **not** coming from port `80` for instance: `ip.port != 80` |

This is an example of a display filter only showing packets coming from the same network (assuming your LAN CIDR is `192.168.1.0/24`):

![LAN CIDR Display Filter](https://lh3.googleusercontent.com/6CwjtGqMl4NkyBbg7vmK86Kl4G_Las0jBT55O4pRbRCLIqkGGJ2HyL5HmUMZWyTu4e1MQ63m5dLaXjlQJ3BFy-nk5NOStU-asvSoo_8vl3lW3Kg2x5eA6JR25pyOb72VyRj1yyh6JF7uwIWNPz4Ad0yZIxLzvIkEsAbOblv4UwuusxrVoKPosDqVad0ndkWthd-WWbhbW21m-wB3aM6z0vLrJ8oKwmVHejE_6fKg8WxlXc-56tp_kYVqHj2Wn0NAmPJZSSTsXUnKHOHvYvXxM1trL5UU0snyeDQ6EDZgCqbGMy1oeEcThQxOSw05GuL8OYS7yLm6nkPSz_6_VzQ5FteQBmpzEh1PqyGhAofMVSaCevCH764jn8SDNHWq0hBVQV9MpCbgTJk4LlQ7mu27J5PqrQb62oC_ifZir4OIApmp8RwMoy6ORsLeUgwvDUj0S9ogKM4LiunfwpQJfDv0dfujnBdmPl_E888jMzOrK6TNfhHl0kSzzJqftX9fR7iMDRC6W4BkQ2sWOuwKjPeCa_MWW1m7LZp5mcztXo7sWSOayTiQp6hoeYRtniDQWWwcLRrxJr-yh0tR0lCZRCJ3uKfMySLxuCHFvl3waw21WGFJuISKTMPlakdSdhR97GNiMWRLH_D3jR9fVlY2g4G8ieMwob8asaSDD7Fhlxh048gzpxhxPBvrjX3tifkcxWlkwvgdH4fJb6DRIF84KxULv4zA0QZizWsc0ubl2iG2MAyRKv8G=w914-h266-no)
