# Домашнее задание к занятию "Система мониторинга Zabbix" - `Согонов Алексей`

### Задание 1

 ```
 sudo apt update
 sudo apt install postgresql
 wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4+debian11_all.deb
 sudo dpkg -i zabbix-release_6.0-4+debian11_all.deb
 sudo apt update
 sudo apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts
 sudo -u postgres createuser --pwprompt zabbix
 sudo -u postgres createdb -O zabbix zabbix
 sudo zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
 sudo systemctl restart zabbix-server apache2
 sudo systemctl enable zabbix-server apache2
```

![Название скриншота 1](https://github.com/SogonovAN/Zabbix-hw/blob/main/1.JPG)`


---

### Задание 2




![Название скриншота 2](https://github.com/SogonovAN/gitlab-hw/blob/main/2.1.JPG)`

![Название скриншота 3](https://github.com/SogonovAN/gitlab-hw/blob/main/2.2.JPG)`

