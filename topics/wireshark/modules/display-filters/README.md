# Display Filters
<!--TOC_START-->
### Contents
- [Overview](#overview)
- [Filtering by Protocol](#filtering-by-protocol)
- [Relational Operators](#relational-operators)
- [Logical Operators](#logical-operators)

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

![ICMP Display Filter](https://lh3.googleusercontent.com/W1j_AtrwMCGBhr3yRUnMc50qgVoltCOT1AnFXXSU9U_8TcSsi1rXDsoPnKiAXxUllgfHsN4dXLB2Bq09aVvPfhwYKgCAQLDoa5hWNnEZ2nvc6HNSB1lZDafJl61jg-ZXwaaRXf687Fyi0viLOO5dUpJoy6IcabiMiKAUDmpjbVXrfg0E11sTT-rFXIF0ecanlyvQl0KsJyugNM3NpoYaDnXSQuhDfCfESy9wF7YHpsMXhadOCk27DVheYB5vEVHFH7GTEmEU8eBxXTI32edzXU14UN1wCUEBv4OqVUEmrt36SweGI1TJ8XW6rT70Zs5Dt1raERiZnLHwYAkG9axjn2SMrCtcXNC1fALajWJ-v5V42qJry_EEs-BLGhwwFPBSWnayEhOHHUHf7GjTVlLIW51ZfVNbdNB9tBkW9s6RNbO6KYXtKe7gtx4WXeDBIVNfy3CK0j8pHdvWDE6K4A6ghpv0a2Gn0ASYGtW13sU90VwR6zmwmYW57Cjm1R9c93amp3SzKoqHEYGJ5fH_qF-lHH7b0UGpLGXeu05K-plJ7lBWJPyOqSMk_2jGwki5hjr-vFMajJu0CrdfdfSD2gQGG-LsUZCgVUbtBS7jUhDeHpOrYpAW6GNNrZ8Gq3hGVlniI9pW_uN3TG8KPuHO47_KGhlWRRXoaiwyiTACFZL187_gveZGYwiTlnC53BA5L4nqzdLXhX1WJ4usBTdZeiBaOVZT8UT-HyAA1EBxeFOhi2eTPWHW=w1168-h339-no)

## Relational Operators
The operators here have the same logic as most programming language.
When the condition that you put into the display filter equates to true, the packet will be shown.

| Operator | Description |
|----------|-------------|
| `eq`, `==`     | Checks if the values of two operands are equal or not, if yes then condition becomes true. An example of this would be checking if the packet is from a certain host: `ip.host == example.com` |
| `!=`     | Checks if the values of two operands are equal or not, if values are not equal then condition becomes true. You could use this to show packets **not** coming from port `80` for instance: `tcp.port != 80` |

This is an example of a display filter only showing packets coming from the same network (assuming your LAN CIDR is `192.168.1.0/24`):

![LAN CIDR Display Filter](https://lh3.googleusercontent.com/6CwjtGqMl4NkyBbg7vmK86Kl4G_Las0jBT55O4pRbRCLIqkGGJ2HyL5HmUMZWyTu4e1MQ63m5dLaXjlQJ3BFy-nk5NOStU-asvSoo_8vl3lW3Kg2x5eA6JR25pyOb72VyRj1yyh6JF7uwIWNPz4Ad0yZIxLzvIkEsAbOblv4UwuusxrVoKPosDqVad0ndkWthd-WWbhbW21m-wB3aM6z0vLrJ8oKwmVHejE_6fKg8WxlXc-56tp_kYVqHj2Wn0NAmPJZSSTsXUnKHOHvYvXxM1trL5UU0snyeDQ6EDZgCqbGMy1oeEcThQxOSw05GuL8OYS7yLm6nkPSz_6_VzQ5FteQBmpzEh1PqyGhAofMVSaCevCH764jn8SDNHWq0hBVQV9MpCbgTJk4LlQ7mu27J5PqrQb62oC_ifZir4OIApmp8RwMoy6ORsLeUgwvDUj0S9ogKM4LiunfwpQJfDv0dfujnBdmPl_E888jMzOrK6TNfhHl0kSzzJqftX9fR7iMDRC6W4BkQ2sWOuwKjPeCa_MWW1m7LZp5mcztXo7sWSOayTiQp6hoeYRtniDQWWwcLRrxJr-yh0tR0lCZRCJ3uKfMySLxuCHFvl3waw21WGFJuISKTMPlakdSdhR97GNiMWRLH_D3jR9fVlY2g4G8ieMwob8asaSDD7Fhlxh048gzpxhxPBvrjX3tifkcxWlkwvgdH4fJb6DRIF84KxULv4zA0QZizWsc0ubl2iG2MAyRKv8G=w914-h266-no)

## Logical Operators
Logical operators allow us to chain conditions to make much more complex and specific filters.
The operators are `AND`, `OR` and `NOT`:

| Operator | Description | Example |
|----------|-------------|---------|
| `and`, `&&` | Called Logical AND operator. If both the operands are true, then the condition becomes true. | Show only traffic on the LAN (192.168.1.x), not internet traffic: `ip.src==192.168.1.0/24 and ip.dst==192.168.1.0/24`
| `or`, `||` | Called Logical OR Operator. If any of the two operands is true, then condition becomes true. | Show only SMTP (TCP port 25) and ICMP Traffic: `tcp.port eq 25 or icmp`
| `!` | Called Logical NOT Operator. Use to reverses the logical state of its operand. If a condition is true then Logical NOT operator will make false. | Show traffic that is **not** TCP: `! tcp`

This screenshot shows the `OR` operator being used to show only TCP and UDP traffic:

![TCP or UDP Display Filter](https://lh3.googleusercontent.com/s7gigEWszpwt0APSZOQkmnKx3lrT3PIKTVXurtak5b8Cmns1tCXupkHebkeMnLE6UEruCNURqRffOVEuAm4D_CdGIB5l322zS64oRfXoH49o-WlPhOPMHxhAFYwjpSLKOmzjf2LXxGwA2Pfi4GhSKH6D0gUNuEBCKTWGmSr6lUbru6yLrdLvNYqsTPeN8xTbnUv8zoNDeDcCGi85kkWoRLnWLiNdh-tmyzR5zm2WwoJjieZj3ppKskV36Lg_alOG-bXWttS2LgMaa6nnIo-qz7dldXMTLt7lmQ_Tp3fNlkh1gmnu7CHhqAHTt3W3ga1qpiCMZXaj4mRr86MZqMAE84ovR5FVLsRQuDIjnUDMJlGhJe1qkNg92hHrbQTPAZ56E98Ag2C1Q3vcfUMXRgOh_TW0TeV8RwUh5mf2ioSS_rvkC5uYSuFJhDWpGUD0Hza0zKa-Jg9P6FAhdJ_M7C-LJ8neDAcJmK9Tq0l7BA73iX9-Lmesg9_425qCaf2mpTBq7G4nfPQYbRjWPqTQrxGi32kllDnWjL2SmFJPPriXf8H3sisGrbSmLMdyq8dnF-BA4Vd2owCG-ubg0WRj5unh_W9kJqedcyo-cZsDNWoDySbv3a3IR2QcUjfoNIV3PvJ1LDbEm-0hqdZnD0Cw8h--_ryYIe9WqvZ7NQFINe1LiI4hTA2YnFtw4MWMlivrdY1zN4Po9AujxCq3ezvJ07lM658GvBfX2_EfB2GXCxgOh4qKNUNH=w1165-h341-no)
