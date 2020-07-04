ansible@ip-172-31-45-112:~$ ansible-playbook apache.yml

PLAY [dev] *****************************************************************************

TASK [Gathering Facts] *****************************************************************
ok: [172.31.38.251]

TASK [install apache2] *****************************************************************
included: /home/ansible/roles/apache/tasks/install-apache.yml for 172.31.38.251

TASK [install apache] ******************************************************************
ok: [172.31.38.251]

TASK [configure apache2 server] ********************************************************
included: /home/ansible/roles/apache/tasks/config-apache.yml for 172.31.38.251

TASK [configure apache server] *********************************************************
changed: [172.31.38.251]

TASK [service apache server] ***********************************************************
included: /home/ansible/roles/apache/tasks/service-apache.yml for 172.31.38.251

TASK [start apache services] ***********************************************************
ok: [172.31.38.251]

TASK [debug] ***************************************************************************
ok: [172.31.38.251] => {
    "msg": " apache installed"
}

RUNNING HANDLER [restart apache2 service] **********************************************
changed: [172.31.38.251]

RUNNING HANDLER [apache : install java] ************************************************
changed: [172.31.38.251]

PLAY [prod] ****************************************************************************

TASK [Gathering Facts] *****************************************************************
ok: [172.31.45.76]

TASK [install nginx] *******************************************************************
included: /home/ansible/roles/nginx/tasks/install-nginx.yml for 172.31.45.76

TASK [install nginx] *******************************************************************
ok: [172.31.45.76]

TASK [configure nginx] *****************************************************************
included: /home/ansible/roles/nginx/tasks/config-nginx.yml for 172.31.45.76

TASK [install nginx server] ************************************************************
ok: [172.31.45.76]

TASK [service nginx server] ************************************************************
included: /home/ansible/roles/nginx/tasks/service-nginx.yml for 172.31.45.76

TASK [service on nginx] ****************************************************************
changed: [172.31.45.76]

TASK [debug] ***************************************************************************
ok: [172.31.45.76] => {
    "msg": " nginx installed"
}

PLAY RECAP *****************************************************************************
172.31.38.251              : ok=10   changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
172.31.45.76               : ok=8    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

