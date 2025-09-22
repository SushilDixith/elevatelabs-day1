# Elevatelabs-day1

An initial network baseline was established by running an Nmap scan to find active hosts and services, followed by a targeted Wireshark analysis of a packet capture (Day 1.pcapng). The scan found three hosts (10.0.2.2, .3, .4) running Windows services (MSRPC, SMB) and a web proxy on port 808. The packet capture confirmed this activity.

Objective
The primary objective was to scan the local network and its range to identify active hosts and enumerate their open services. A secondary objective was to use the Day 1.pcapng packet capture to passively analyze the network traffic for baselining purposes.

Methodology
A combined approach was used: first, an Nmap scan identified live hosts and open ports on the network. The results from this scan were then used to guide a focused, passive analysis of the Day 1.pcapng file in Wireshark.

Findings
Nmap Scan: The scan identified three active hosts: 
10.0.2.2
10.0.2.3
10.0.2.4
All three hosts exposed the same open TCP ports
135 (msrpc)
445 (microsoft-ds)
808 (ccproxy-http).

Wireshark Analysis
The packet capture analysis confirmed the Nmap findings. The traffic included standard ARP and DHCP requests for network setup. Targeted filters confirmed active SMB (port 445) and MSRPC (port 135) conversations between the identified hosts, which is typical for a Windows network. Traffic was also confirmed on the proxy port (808).
