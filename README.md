# Домашнее задание к занятию "`Система мониторинга Zabbix. Часть 2`" - `Попов Игорь`

---

### Задание 1

Скриншот шаблона "Test_popov" в нем сощздал два Itema: Загрузке CPU (CPU_load) и загрузка памяти (RAM_load)

![Скрин шаблона](https://github.com/garkitt/popov-zabbix/blob/9892ecfb89d9000b0f921af0d34b4eab1e5cb28c/img/Temp_1.png)`


---

### Задание 2

На скрине видим подклюбченные агенты
![Агенты](https://github.com/garkitt/popov-zabbix/blob/b1f0c439ec821207a070bf84242300d2f27ef6c4/img/new2-1.png)


Лог Агентов


![Логагента1](https://github.com/garkitt/popov-zabbix/blob/ad26399b2bba918a4cda23ce92c2607a4ece31e7/img/log_1.png)



![Логагентв2](https://github.com/garkitt/popov-zabbix/blob/ad26399b2bba918a4cda23ce92c2607a4ece31e7/img/log_2.png)


Скриншот раздела Monitoring > Latest data

![Работа1](https://github.com/garkitt/popov-zabbix/blob/c815935e213edf2f266d53358589dfaf02da6783/img/Latest_data.png)


![Работа2](https://github.com/garkitt/popov-zabbix/blob/c815935e213edf2f266d53358589dfaf02da6783/img/Latest_data_1.png)


Использовал следующие команды для  установки Агента (установил на Debian)

1) wget https://repo.zabbix.com/zabbix/7.0/debian/pool/main/z/zabbix-release/zabbix-release_latest_7.0+debian13_all.deb
2) dpkg -i zabbix-release_latest_7.0+debian13_all.deb
3) apt update
4) apt install zabbix-agent - установка агента
5) sudo systemctl restart zabbix-agent.service
6) sudo nano /etc/zabbix/zabbix_agentd.conf - файл конфигурации Агента. Прописываем IP zabbix-сервера.
7) sudo systemctl restart zabbix-agent.service
8) tail -f /var/log/zabbix/zabbix_agentd.log - смотрим логи