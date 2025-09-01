NETWORK DIAGRAM
---------------

Company Network (production/test lab for the company)
- Zabbix Server (172.16.29.140)
  - Role: Zabbix Server (server + frontend + agent)
  - Services: Zabbix Server (listen 10051), Web UI (Apache), DB (MySQL)
  - Accessible from company hosts (router, server) on management network

- Router (172.16.29.138)
  - Role: Company network device (monitored)
  - Zabbix Agent: listening on 10050
  - Purpose: routing/edge device for company VMs

- Server (172.16.29.137)
  - Role: Company application/server (monitored)
  - Zabbix Agent: listening on 10050
  - Purpose: services for the company lab

Attacker (isolated, OUT-OF-BAND)
- Attacker VM (172.16.29.141)
  - Role: adversary machine used for attack testing only
  - Network: isolated host-only or separate VLAN; no direct management access to company hosts
  - Purpose: offensive testing/validation; must not be reachable from company network except via controlled lab bridges

ASCII diagram (simple):

Zabbix Server (172.16.29.140)  <---management--->  Router (172.16.29.138)
                                   |
                                   v
                                Server (172.16.29.137)

Attacker (172.16.29.141)  -- isolated (host-only / separate VLAN) --X--> (no direct access to company hosts)

Notes:
- Zabbix Server collects passive checks from agents on ports 10050 and receives active checks on 10051.
- Ensure firewall rules restrict the Attacker VM so it cannot reach management ports of company hosts unless intentionally allowed for a test.
- Keep IP assignments static for reproducibility and documentation.

