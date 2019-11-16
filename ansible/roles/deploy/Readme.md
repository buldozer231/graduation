ansible-playbook roles.yml
--tags deploy
--tags erase
--tags install_nginx(/nano/gzip/...)
--tags remove_nginx(/nano/gzip/....)
--tags start_nginx(restart/stop)
