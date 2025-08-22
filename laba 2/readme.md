# **Лабораторная работа. Просмотр таблицы MAC-адресов коммутатора**
# Топология сети  
<img width="454" height="238" alt="image" src="https://github.com/user-attachments/assets/17424118-cece-41e2-ae27-e4a67dfebbea" />  

>Таблица адресации

| Устройство | Интерфейс | ip адрес         | Маска подсети  |
|------------|-----------|------------------|----------------|
|     S1     |   Vlan 1  |  192.168.1.11    | 255.255.255.0  |
|     S2     |   Vlan 1  |  192.168.1.12    | 255.255.255.0  |
|     PC-A   |    NIC    |  192.168.1.1     | 255.255.255.0  |
|     PC-B   |    NIC    |  192.168.1.2     | 255.255.255.0  |  

>Шаг 2. Настройте узлы ПК.

>PC-A

<img width="702" height="293" alt="image" src="https://github.com/user-attachments/assets/465cd5a7-78ad-4764-88ec-38e700ac5320" />  

>PC-B

<img width="701" height="292" alt="image" src="https://github.com/user-attachments/assets/2d2957a6-9237-4dbb-85f3-55fd782c29f6" />  

>Шаг 3. Выполните инициализацию и перезагрузку коммутаторов.

Switch1

<img width="629" height="152" alt="image" src="https://github.com/user-attachments/assets/ae1cdb6d-cc01-46ef-a162-3caaea129aac" />

Switch2

<img width="604" height="198" alt="image" src="https://github.com/user-attachments/assets/9d38642b-8a58-406c-9737-dddaac9347d1" />  

>Шаг 4. Настройте базовые параметры каждого коммутатора.

>a.	Настройте имена устройств в соответствии с топологией.

<img width="430" height="95" alt="image" src="https://github.com/user-attachments/assets/da965a5b-89bf-43e8-8749-6e074d80293f" />  
<img width="451" height="93" alt="image" src="https://github.com/user-attachments/assets/fecccff8-b978-4db9-a1ca-8f13d1a39710" />  

>b.	Настройте IP-адреса, как указано в таблице адресации.

<img width="466" height="132" alt="image" src="https://github.com/user-attachments/assets/58889652-5e70-4d2f-b3ea-c1184c992f5f" />  

<img width="440" height="131" alt="image" src="https://github.com/user-attachments/assets/2e9866a5-3af7-4cd9-a65b-fab6c62b9eb6" />  

>c.	Назначьте cisco в качестве паролей консоли и VTY.

<img width="459" height="145" alt="image" src="https://github.com/user-attachments/assets/524369cd-d887-47b1-bb17-55d55d48f76f" />  

<img width="413" height="125" alt="image" src="https://github.com/user-attachments/assets/0e64f0ba-4b46-412c-a6f5-7b506841de79" />  

>d.	Назначьте class в качестве пароля доступа к привилегированному режиму EXEC.

<img width="451" height="106" alt="image" src="https://github.com/user-attachments/assets/c6db729f-89f0-40fd-a223-c09abd11f37f" />  

<img width="434" height="87" alt="image" src="https://github.com/user-attachments/assets/a91a0291-4b5b-440f-aef4-c7f6d772650e" />  

>Шаг 1. Запишите МАС-адреса сетевых устройств.

>a.	Откройте командную строку на PC-A и PC-B и введите команду ipconfig /all.

>Назовите физические адреса адаптера Ethernet.

>MAC-адрес компьютера PC-A: **00D0.FFB1.229C**

>MAC-адрес компьютера PC-B: **00E0.B0CE.DB2E**

>b.	Подключитесь к коммутаторам S1 и S2 через консоль и введите команду show interface F0/1 на каждом коммутаторе.

>Назовите адреса оборудования во второй строке выходных данных команды (или зашитый адрес — bia).

>МАС-адрес коммутатора S1 Fast Ethernet 0/1: **address is 00e0.a322.0a01 (bia 00e0.a322.0a01)**

>МАС-адрес коммутатора S2 Fast Ethernet 0/1: **address is 00e0.f746.9d01 (bia 00e0.f746.9d01)**

>Шаг 2. Просмотрите таблицу МАС-адресов коммутатора.
Подключитесь к коммутатору S2 через консоль и просмотрите таблицу МАС-адресов до и после тестирования сетевой связи с помощью эхо-запросов.

>a.	Подключитесь к коммутатору S2 через консоль и войдите в привилегированный режим EXEC.

<img width="280" height="143" alt="image" src="https://github.com/user-attachments/assets/d2288e6e-c596-49c3-8b48-d64e8f609894" />  

>b.	В привилегированном режиме EXEC введите команду show mac address-table и нажмите клавишу ввода.

>результат вывода команды show mac address-table

<img width="356" height="131" alt="image" src="https://github.com/user-attachments/assets/35f4ac8f-925a-406c-9387-e43c4873436f" />  

>Записаны ли в таблице МАС-адресов какие-либо МАС-адреса?

>Да

>Какие МАС-адреса записаны в таблице?

**00D0.FFB1.229C**  
**00e0.f746.9d01**  
>С какими портами коммутатора они сопоставлены и каким устройствам принадлежат?

С портами Fa0/6 и Fa0/1, mac adress **00D0.FFB1.229C** принадлежит PC-A, mac adress **00e0.f746.9d01**  принадлежит комутатору S2  
>Если вы не записали МАС-адреса сетевых устройств в шаге 1, как можно определить, каким устройствам принадлежат МАС-адреса, используя только выходные данные команды show mac address-table? Работает ли это решение в любой ситуации?

Выходные данные команды show mac address-table показывают порт, на котором был получен MAC-адрес. В большинстве случаев это позволит определить, какому сетевому устройству принадлежит MAC-адрес  
>Шаг 3. Очистите таблицу МАС-адресов коммутатора S2 и снова отобразите таблицу МАС-адресов.

>a.	В привилегированном режиме EXEC введите команду clear mac address-table dynamic и нажмите клавишу Enter.
>S2# clear mac address-table dynamic
>b.	Снова быстро введите команду show mac address-table.

>Указаны ли в таблице МАС-адресов адреса для VLAN 1? Да

>Указаны ли другие МАС-адреса? нет

<img width="351" height="141" alt="image" src="https://github.com/user-attachments/assets/af194247-bfb2-45e0-a8c7-988fe4af78ca" />  

>Через 10 секунд введите команду show mac address-table и нажмите клавишу ввода. Появились ли в таблице МАС-адресов новые адреса? нет

<img width="378" height="119" alt="image" src="https://github.com/user-attachments/assets/3130218c-3a23-4303-a14d-d6c10cee191f" />  

>Шаг 4. С компьютера PC-B отправьте эхо-запросы устройствам в сети и просмотрите таблицу МАС-адресов коммутатора.

>a.	На компьютере PC-B откройте командную строку и еще раз введите команду arp -a.

<img width="174" height="33" alt="image" src="https://github.com/user-attachments/assets/681d6058-e86b-4dbb-966e-1a92c48237da" />  

В кэше ARP может не быть записей, или он может иметь сопоставление IP-адреса шлюза с MAC-адресом.  
>b.	Из командной строки PC-B отправьте эхо-запросы на компьютер PC-A, а также коммутаторы S1 и S2.
<img width="432" height="572" alt="image" src="https://github.com/user-attachments/assets/72d827ff-73bc-419f-bdfa-fd0ba80e4027" />

>Вопрос: От всех ли устройств получены ответы? Да

>c.	Подключившись через консоль к коммутатору S2, введите команду show mac address-table.

<img width="400" height="330" alt="image" src="https://github.com/user-attachments/assets/71e991b3-9d73-4c07-92ac-62b6877ea1ac" />

>Откройте окно конфигурации
>Вопрос: Добавил ли коммутатор в таблицу МАС-адресов дополнительные МАС-адреса? ДА Если да, то какие адреса и устройства?
>
>Адрес **00e0.b0ce.db2e** принадлежит компьютеру PC-B; адрес **00e0.a322.0a01** принадлежит комутатору S2

>На компьютере PC-B откройте командную строку и еще раз введите команду arp -a.
Вопрос: Появились ли в ARP-кэше компьютера PC-B дополнительные записи для всех сетевых устройств, которым были отправлены эхо-запросы?

>Да

<img width="443" height="89" alt="image" src="https://github.com/user-attachments/assets/37ea439c-6d7a-4083-9a83-981650b839a2" />



























