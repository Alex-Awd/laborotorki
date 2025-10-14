# Шаг 1. Создайте сеть согласно топологии.
<img width="715" height="457" alt="image" src="https://github.com/user-attachments/assets/ea415fc9-4162-4d72-9b18-7e83bcd4f46c" />  

# Шаг 4. Настройка интерфейсов и маршрутизации для обоих маршрутизаторов.
### a.	Настройте интерфейсы G0/0/0 и G0/1 на R1 и R2 с адресами IPv6, указанными в таблице выше.  
<img width="417" height="420" alt="image" src="https://github.com/user-attachments/assets/090110ad-4fb8-4e6f-aee2-237458baf016" />

### b.	Настройте маршрут по умолчанию на каждом маршрутизаторе, который указывает на IP-адрес G0/0/0 на другом маршрутизаторе.  
<img width="433" height="75" alt="image" src="https://github.com/user-attachments/assets/ee491647-9ee3-470d-88f1-22a106bebb10" />  

### c.	Убедитесь, что маршрутизация работает с помощью пинга адреса G0/0/1 R2 из R1  
<img width="625" height="138" alt="image" src="https://github.com/user-attachments/assets/ca480b1f-ce4d-4165-bf80-7880e19c34f9" />  

# Часть 2. Проверка назначения адреса SLAAC от R1  
>В части 2 вы убедитесь, что узел PC-A получает адрес IPv6 с помощью метода SLAAC.
Включите PC-A и убедитесь, что сетевой адаптер настроен для автоматической настройки IPv6.
Через несколько минут результаты команды ipconfig должны показать, что PC-A присвоил себе адрес из сети 2001:db8:1::/64.
<img width="597" height="224" alt="image" src="https://github.com/user-attachments/assets/b946d7a6-fdb1-4aad-a756-2224bf549d17" />

# Часть 3. Настройка и проверка сервера DHCPv6 на R1
В части 3 выполняется настройка и проверка состояния DHCP-сервера на R1. Цель состоит в том, чтобы предоставить PC-A информацию о DNS-сервере и домене.
### Шаг 1. Более подробно изучите конфигурацию PC-A.  
<img width="634" height="297" alt="image" src="https://github.com/user-attachments/assets/9a11e627-7da7-4783-a41f-d861d2d98a62" />  

#Шаг 2. Настройте R1 для предоставления DHCPv6 без состояния для PC-A.
### a.	Создайте пул DHCP IPv6 на R1 с именем R1-STATELESS. В составе этого пула назначьте адрес DNS-сервера как 2001:db8:acad: :1, а имя домена — как stateless.com.
<img width="415" height="64" alt="image" src="https://github.com/user-attachments/assets/cdff2629-e7d2-4f92-a29c-33be0dcb3c64" />

b.	Настройте интерфейс G0/0/1 на R1, чтобы предоставить флаг конфигурации OTHER для локальной сети R1 и укажите только что созданный пул DHCP в качестве ресурса DHCP для этого интерфейса.

<img width="370" height="62" alt="image" src="https://github.com/user-attachments/assets/8870e0b1-6d82-4c5c-b31c-b7fb8dcc6df5" />

### c.	Сохраните текущую конфигурацию в файл загрузочной конфигурации.
### d.	Перезапустите PC-A.
### e.	Проверьте вывод ipconfig /all  
<img width="630" height="285" alt="image" src="https://github.com/user-attachments/assets/45ee1f35-c832-4965-86aa-60413ba4136a" />  

# Часть 4. Настройка сервера DHCPv6 с сохранением состояния на R1
В части 4 настраивается R1 для ответа на запросы DHCPv6 от локальной сети на R2.
### a.	Создайте пул DHCPv6 на R1 для сети 2001:db8:acad:3:aaa::/80. Это предоставит адреса локальной сети, подключенной к интерфейсу G0/0/1 на R2. В составе пула задайте DNS-сервер 2001:db8:acad: :254 и задайте доменное имя STATEFUL.com.
Откройте окно конфигурации

<img width="508" height="87" alt="image" src="https://github.com/user-attachments/assets/7e0f0e58-e55d-42fc-8aa8-baa94107569d" />

### b.	Назначьте только что созданный пул DHCPv6 интерфейсу g0/0/0 на R1.

<img width="389" height="49" alt="image" src="https://github.com/user-attachments/assets/d5eb895a-db95-45c9-ab76-19400992d39f" />  
# Часть 5. Настройка и проверка ретрансляции DHCPv6 на R2.
В части 5 необходимо настроить и проверить ретрансляцию DHCPv6 на R2, позволяя PC-B получать адрес IPv6.
### Шаг 1. Включите PC-B и проверьте адрес SLAAC, который он генерирует.
<img width="633" height="273" alt="image" src="https://github.com/user-attachments/assets/14737134-ccdc-47e6-b91f-e76b7b81450d" />  

# Шаг 2. Настройте R2 в качестве агента DHCP-ретрансляции для локальной сети на G0/0/1.
### a.	Настройте команду ipv6 dhcp relay на интерфейсе R2 G0/0/1, указав адрес назначения интерфейса G0/0/0 на R1. Также настройте команду managed-config-flag .
Откройте окно конфигурации

<img width="556" height="56" alt="image" src="https://github.com/user-attachments/assets/0289b4de-1fcd-46b8-9d70-568e4ee89f37" />

# Шаг 3. Попытка получить адрес IPv6 из DHCPv6 на PC-B.
### a.	Перезапустите PC-B.
### b.	Откройте командную строку на PC-B и выполните команду ipconfig /all и проверьте выходные данные, чтобы увидеть результаты операции ретрансляции DHCPv6.  
<img width="637" height="223" alt="image" src="https://github.com/user-attachments/assets/a42b3d64-fbd8-4864-b044-aaa45baaf45e" />  

> Доп указания

<img width="533" height="207" alt="image" src="https://github.com/user-attachments/assets/067eebfa-302f-417f-b9af-ea12253454ec" />  
<img width="633" height="284" alt="image" src="https://github.com/user-attachments/assets/b601918e-fcf3-4ad0-b6b5-b3e60f86edde" /> 
<img width="523" height="372" alt="image" src="https://github.com/user-attachments/assets/dd8b26a3-db32-45e9-a430-b6b98aed7165" />
















