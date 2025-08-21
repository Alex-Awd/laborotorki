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















