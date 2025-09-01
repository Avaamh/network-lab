Connectivity:

172.16.29.141 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
172.16.29.138 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
172.16.29.140 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
172.16.29.137 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}




Agents status:


PLAY [Install and configure Zabbix Agent on Router and Server] *****************

TASK [Gathering Facts] *********************************************************
ok: [172.16.29.138]
ok: [172.16.29.137]

TASK [Configure Zabbix Agent (Passive Server)] *********************************
ok: [172.16.29.138]
ok: [172.16.29.137]

TASK [Configure Zabbix Agent (Active Server)] **********************************
ok: [172.16.29.137]
ok: [172.16.29.138]

TASK [Configure Hostname] ******************************************************
ok: [172.16.29.138]
ok: [172.16.29.137]

TASK [Ensure Zabbix Agent service is enabled and started] **********************
ok: [172.16.29.138]
ok: [172.16.29.137]

TASK [Verify Zabbix Agent service status] **************************************
ok: [172.16.29.137]
ok: [172.16.29.138]

TASK [Show agent status] *******************************************************
ok: [172.16.29.138] => {
    "msg": "Zabbix Agent on 172.16.29.138 is active"
}
ok: [172.16.29.137] => {
    "msg": "Zabbix Agent on 172.16.29.137 is active"
}

PLAY RECAP *********************************************************************
172.16.29.137              : ok=7    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   
172.16.29.138              : ok=7    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   


