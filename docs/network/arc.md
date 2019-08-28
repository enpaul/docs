# Architecture

## Overview

My homelab, and by extension my home network, needs to meet a few requirements:

* Provide secure internet connectivity for myself and my roommates *(secure agents)*
* Provide secure internet connectivity for house guests, family members, party guests, etc *(insecure agents)*
* Provide secure intranet connectivity between homelab agents
* Provide secure access to internal homelab agents from internet agents
* Restrict access between agents on disparate network segments
* Restrict access to intranet resources from internet agents
* Restrict access to intranet resources from physically proximate agents

To meet these requirements I settled on a three-segment network, each operating at a
different security zone. This also has the added advantage of not over complicating
things.

|                       | Subnet           | DNS Zone      | Interop                                     |
| --------------------- | ---------------- | ------------- | ------------------------------------------- |
| Homelab Domain        | `10.42.101.0/24` | `net.enp.one` | Connectivity to Secure Agents               |
| Secure Agent Domain   | `10.42.100.0/24` | `tre2.local`  | Connectivity to Homelab and Insecure Agents |
| Insecure Agent Domain | `10.42.100.0/24` | `tre2.local`  | Connectivity to Secure Agents               |

!!! note
    In addition to the above subnets I also have `10.42.102.0/24` reserved for
    future VPN/remote connectivity work.

!!! question
    Why use `10.42.100.0/24` through `10.42.102.0/24`? Choosing a somewhat obtuse range
    of subnets, as opposed to `10.0.1.0/24`, decreases the likelihood of an IP conflict
    when connecting to 3rd part VPNs or integrating with other networks.

!!! todo
    Audit and restructure the firewall separation between the homelab domain and other
    domains. Right now the firewall is far too permissive.

## Domain Separation

Note that the word "*domain*" here is used to denote something closer to a traditional
*organizational unit* (OU) than a literal DNS domain or subnet. A "*domain*" in this
sense is a combination of a logical network segment, a L2/L3 network, and an isolated
security zone.

### Homelab Domain

This is the core domain where servers, applications, storage arrays, management devices,
and virtual machines all live. Basically **a)** anything I don't want my roommates
messing with and **b)** anything I don't want messing with my roommates if it goes
haywire.

### Secure Agent Domain

Secure agents, also known as trusted agents, are devices owned by people that I trust
are not going to (intentionally) compromise my network. This includes personal
computers, XBox's, phones, and Raspberry Pi's.

### Insecure Agent Domain

No man's land. The wild west. Anything and everything and something in between. My
friend's grandmother's ten year old unpatched Windows XP machine. A ruggedized computer
stamped "confidential" found in the back alley. An Amazon Alexa. God only knows what is
going to end up on this subnet, but I know I don't want it touching any of my stuff.

---

*Last updated `{{ git_revision_date }}`*
