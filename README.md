# Домашнее задание к занятию "`Система мониторинга Zabbix`" - `Попов Игорь`

---

### Задание 1

![Скрин Админки](https://github.com/garkitt/popov-zabbix/blob/4e6b0e682d6d5171d6f7169e3a650cf68add7a87/img/admika.png)`

Использовал следующие команлды для установки Zabbix
1) wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.0+ubuntu24.04_all.deb
2) dpkg -i zabbix-release_latest_7.0+ubuntu24.04_all.deb
3) apt update
4) apt install zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-apache-conf zabbix-sql-scripts
5) sudo -u postgres createuser --pwprompt zabbix
6) sudo -u postgres createdb -O zabbix zabbix
7) zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
8) systemctl restart zabbix-server apache2
9) systemctl enable zabbix-server apache2
---

### Задание 2

На скрине видим подклюбченные агенты
![Скрин Админки](https://github.com/garkitt/popov-zabbix/blob/111b9580080c033eff2293cebaa69e505c57524f/img/new2-1.png)


Лог Агентов
[Скрин Админки](https://github.com/garkitt/popov-zabbix/blob/ad26399b2bba918a4cda23ce92c2607a4ece31e7/img/log_1.png)
[Скрин Админки](https://github.com/garkitt/popov-zabbix/blob/ad26399b2bba918a4cda23ce92c2607a4ece31e7/img/log_2.png)


Скриншот раздела Monitoring > Latest data

[Скрин Админки](https://github.com/garkitt/popov-zabbix/blob/c815935e213edf2f266d53358589dfaf02da6783/img/Latest_data.png)
[Скрин Админки](https://github.com/garkitt/popov-zabbix/blob/c815935e213edf2f266d53358589dfaf02da6783/img/Latest_data_1.png)


Использовал следующие команды
1) tail -f /var/log/zabbix/zabbix_agentd.log 
2) sudo systemctl restart zabbix-agent.service
3) systemctl status zabbix-agent.service
