---

copyright:
  years: 1994, 2017-2019
lastupdated: "2019-04-26"

keywords: Use SSL VPN Navigate, private IP address, private VLAN, IaaS VPN

subcollection: iaas-vpn

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:generic: data-hd-programlang="generic"}

# Use SSL VPN
{:#use-ssl-vpn}

1. Navigate to the **SSL VPN Login** link in the Customer Portal by selecting to **Support > SSL VPN Login** from the Navigation menu, then enter your credentials
2. The SSL VPN tunnel is established when you observe the "A" in your task bar.
3. Congrats - you are now in your private VLAN.

## Now I'm connected...what do I do?
{:#now-im-connected-what-do-i-do}

1. Use SSH or RDC (terminal services) to connect to your server's private IP address (10.x.x.x) for server management.
2. To utilize remote console or reboot functions, connect to your IPMI 2.0 Card through the SuperMicro software - refer to the [Customer Portal ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://{DomainName}/) for download instructions.
3. You can map a drive to your server (Windows) or mount a drive to your server (Red Hat).

## Tips and tricks
{:#ssl-vpn-tips-tricks}

1. Your IPMI IP and Private IP are one digit apart - don't get them mixed up.
2. You cannot use SSH or RDC to connect to the IPMI card, you must use the software.
3. Your IPMI IP and Private IP are found in your hardware section under each **Server**.
4. Your IPMI card "listens" on the private IP interface and re-directs IPMI traffic to the IPMI card.

## Product-specific IPMI instructions
{:#product-specific-impi-instructions}

* For more information about using IPMI on a CIFS share, see [Mounting an ISO on a bare metal server](/docs/bare-metal?topic=bare-metal-bm-mount-iso#bm-mount-iso-opt-1).
* For more information about using IPMI with VMWare, see [Installing VMware vSphere ESXi via Remote Console and Virtual Media](/docs/infrastructure/vmware?topic=VMware-installing-vsphere-esxi).

* For more information about using IPMI with IBM POWER hardware, see [Installing IPMItool](https://www.ibm.com/support/knowledgecenter/TI0003H/p8eih/p8eih_ipmitool.htm).

**Warning:**

If you disable `eth0` (which is the private network interface), you will lose all IPMI functionality including monitoring, remote console, remote reboot, and more. If you want to lock down access to the private interface, see our list of allowed IP addresses you can enter into your IP Tables or Server Firewall.
