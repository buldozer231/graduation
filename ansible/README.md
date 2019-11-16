Chorniy Maksim

ansible-playbook roles.yml
--tags deploy
--tags erase
--tags install_nginx(/nano/gzip/...)
--tags remove_nginx(/nano/gzip/....)
--tags start_nginx(restart/stop)

root@maxim-pc:/etc/ansible# ansible-playbook -l rhel playbooks/roles.yml --tags deploy,start_nginx,restart_nginx && ansible-playbook -l rhel playbooks/roles.yml --tags erase && git commit -m "Done!" && git push origin master

PLAY [all]

TASK [Gathering Facts]
ok: [rhel1]
ok: [rhel2]

TASK [deploy: Checking tasks]
ok: [rhel2]
ok: [rhel1]

TASK [deploy: Pre-install check Nginx]
ok: [rhel1]
ok: [rhel2]

TASK [deploy: Pre-install check Nano]
ok: [rhel1]
ok: [rhel2]

TASK [deploy: Pre-install check Gzip]
skipping: [rhel1]
skipping: [rhel2]

TASK [deploy: Pre-install check Zip]
ok: [rhel1]
ok: [rhel2]

TASK [deploy: Pre-install check Unzip]
ok: [rhel1]
ok: [rhel2]

TASK [deploy: Nginx Install]
changed: [rhel2]
changed: [rhel1]

TASK [deploy: Start Nginx]
changed: [rhel1]
changed: [rhel2]

TASK [deploy: Restart Nginx]
changed: [rhel1]
changed: [rhel2]

TASK [deploy: Nano Install]
changed: [rhel1]
changed: [rhel2]

TASK [deploy: Zip Install]
changed: [rhel1]
changed: [rhel2]

TASK [deploy: Gzip Install]
skipping: [rhel1]
skipping: [rhel2]

TASK [deploy: Unzip Install]
ok: [rhel1]
ok: [rhel2]

PLAY RECAP
rhel1 : ok=12 changed=5  unreachable=0  failed=0  skipped=2  rescued=0  ignored=0
rhel2 : ok=12 changed=5  unreachable=0  failed=0  skipped=2  rescued=0  ignored=0

PLAY [all]

TASK [Gathering Facts]
ok: [rhel2]
ok: [rhel1]

TASK [deploy: Checking tasks]
ok: [rhel2]
ok: [rhel1]

TASK [deploy: Pre-remove check Nginx]
ok: [rhel1]
ok: [rhel2]

TASK [deploy: Pre-remove check Nano]
ok: [rhel1]
ok: [rhel2]

TASK [deploy: Pre-remove check Gzip]
ok: [rhel1]
ok: [rhel2]

TASK [deploy: Pre-remove check Zip]
ok: [rhel1]
ok: [rhel2]

TASK [deploy: Pre-remove check Unzip]
ok: [rhel1]
ok: [rhel2]

TASK [deploy: Nginx Remove] 
changed: [rhel1]
changed: [rhel2]

TASK [deploy: Nano Remove]
changed: [rhel1]
changed: [rhel2]

TASK [deploy: Zip Remove]
changed: [rhel1]
changed: [rhel2]

TASK [deploy: Gzip Remove]
skipping: [rhel1]
skipping: [rhel2]

TASK [deploy: Unzip Remove]
changed: [rhel1]
changed: [rhel2]

PLAY RECAP
rhel1 : ok=11 changed=4  unreachable=0  failed=0  skipped=1  rescued=0  ignored=0
rhel2 : ok=11 changed=4  unreachable=0  failed=0  skipped=1  rescued=0  ignored=0

[master 969d45e] Done!
