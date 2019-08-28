# ENP.One Documentation

> A system is only as good as its documentation  *-- A proverb, probably*

> Some documentation is better than no documentation, but no documentation is better than wrong documentation  *-- me, all the time*

My homelab has gotten well out of hand. Back in 2014 when I pulled a busted up server out an actual dumpster I had no idea that five years later I'd be running two clustered servers, a control node, a dozen different services, and have two different uplink points. Halp.

But here I am. And I figured I'd best start documenting this stuff before I lose my mind and everything flies apart.

Note that these docs **do not** cover deployment/management details. Please see the [Ansible repository](https://vcs.enp.one/omni/omni-ansible/). 

## Why have a homelab?

Excellent question. I maintain my homelab for exactly three reasons:

* Education
* Fun
* Independence

### Education

My homelab provides me opportunities to learn how new tools and environments work in a context where I have more control than I do in a professional setting. This lets me try things out to see how they work without needing to get approval or risk breaking something important. I am definitely a "learn by doing" person.

As a result of this, the state of my homelab largely reflects the state of my current employer. When I worked at a company that ran an MS Active Directory core my homelab ran Active Directory and Hyper-V. Now that I am at an organization that runs a Linux stack, I run CentOS and KVM.

### Fun

This one shouldn't need explanation. I find maintaining this equipment fun in a challenging sort of way. To me it's a challenge of looking at something like Google Drive and saying "I bet I could host that myself". Which leads me to my final point...

### Independence

I believe strongly in people's right to a free and open internet, and I believe that private corporations owning infrastructure critical to everyday user's ability to participate in online environments is actively hindering that. And while I certainly don't think everyone should run their own homelab, it is the way I choose to solve what I see as a problem.

## External Links

* [Personal Homepage](https://enpaul.net/)
* [Version Control System](https://vcs.enp.one/)
* [Cloud File System](https://cfs.enp.one/)
* [Secure Storage Vault](https://ssv.enp.one/)
* [Content Delivery Network](https://cdn.enp.one/)

 

---

*Last updated `{{ git_revision_date }}`*