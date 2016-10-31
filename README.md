# findject
Detect TCP packet injection attacks

findject.py

Findject is a simple pyhton script that can find injected TCP packets in HTTP sessions, such as the QUANTUMINSERT Man-on-the-Side (MOTS) attacks. Packet injections can be detected with some IDS solutions, such as Bro and Suricata. However, we noticed that these solutions didn't properly detect all MOTS attacks - which is why findject.py was created. Other noteworthy tools for detecting packet injection attacks are HoneyBadger and qisniff.

Findject is open source software and is released under the GNU General Public License version 2 (GPLv2).

#Usage

##Execute findject like this:

python findject.py capturefile.pcap
Example execution with no injections found:

python findject.py /nsm/pcap/*.pcap
opening /nsm/pcap/000.pcap - no injections
opening /nsm/pcap/001.pcap - no injections
opening /nsm/pcap/002.pcap - no injections
opening /nsm/pcap/003.pcap - no injections
opening /nsm/pcap/004.pcap - no injections
opening /nsm/pcap/005.pcap - no injections
opening /nsm/pcap/006.pcap - no injections
opening /nsm/pcap/007.pcap - no injections
opening /nsm/pcap/008.pcap - no injections
opening /nsm/pcap/009.pcap - no injections
opening /nsm/pcap/010.pcap - no injections
opening /nsm/pcap/011.pcap - no injections
Example execution with packet injection detected:

python findject.py /nsm/pcap/id1-cn.pcap
opening /nsm/pcap/id1-cn.pcap
PACKET INJECTION 42.96.141.35:80-192.168.1.254:1337 SEQ : 133704711
FIRST :
'HTTP/1.1 403 Forbidden\r\nServer: Beaver\r\nCache-Control: no-cache\r\nContent-Type: text/html\r\nContent-Length: 594\r\nConnection: close\r\n\r\n[...]'
LAST :
'HTTP/1.1 200 OK\r\nContent-Type: text/html\r\nContent-Length: 207\r\nConnection: close\r\n\r\n[...]'
Dependencies

Findject runs on any OS that supports Python, i.e. Windows, Linux and Mac OS X.
You need the following software installed to run findject.py:

Python 2.6 or 2.7
dpkt
repoze.lru
The dependencies can be installed using PIP like this:
pip install dpkt
pip install repoze.lru
Download

Findject can be downloaded from the following URL: https://www.netresec.com/?download=findject

PCAP files

We have linked several publicly available PCAP files containing TCP packet injection attacks on our PCAP repository page. Scroll down to the "Packet Injection Attacks / Man-on-the-Side Attacks" segment to find the example packet captures.
