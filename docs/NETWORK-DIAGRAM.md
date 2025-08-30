# Network Topology

Router VM (192.168.56.1)
   |
   |-- Server VM (192.168.56.10)
   |      - LDAP
   |      - Samba
   |      - DNS
   |
   |-- Zabbix VM (192.168.56.20)
   |      - Zabbix Server
   |
   |-- Attacker VM (192.168.56.30)
          - Kali Linux / penetration testing
