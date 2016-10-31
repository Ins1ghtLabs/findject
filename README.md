# findject
Detect TCP packet injection attacks

findject.py

Findject is a simple pyhton script that can find injected TCP packets in HTTP sessions, such as the QUANTUMINSERT Man-on-the-Side (MOTS) attacks. Packet injections can be detected with some IDS solutions, such as Bro and Suricata. However, we noticed that these solutions didn't properly detect all MOTS attacks - which is why findject.py was created. Other noteworthy tools for detecting packet injection attacks are HoneyBadger and qisniff.

Findject is open source software and is released under the GNU General Public License version 2 (GPLv2).

Forked from https://www.netresec.com/?page=findject


##Changelog:
Added support for BSD's DLT_NULL datalink
