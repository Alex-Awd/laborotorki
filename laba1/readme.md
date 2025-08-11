# **Лабораторная работа. Базовая настройка коммутатора**

1.Часть 1. Создание сети и проверка настроек коммутатора по умолчанию

  >b.Изучите текущий файл running configuration.

  Сколько интерфейсов FastEthernet имеется на коммутаторе 2960?.  
  Ответ **24**  
  Сколько интерфейсов Gigabit Ethernet имеется на коммутаторе 2960?  
  Ответ **2**  
  Каков диапазон значений, отображаемых в vty-линиях?  
  Ответ диапозон от 0 до 4 и от5 до 15.
>c.Изучите файл загрузочной конфигурации (startup configuration), который содержится в энергонезависимом ОЗУ (NVRAM).
>Вопрос:Почему появляется это сообщение?

Switch#startup configuration  
^  
% Invalid input detected at '^' marker.  
Данное собщение появляется потому что ошибка в коменде, правильная команда show startup-config  
>d.	Изучите характеристики SVI для VLAN 1.

Switch#show interfaces vlan 1
Vlan1 is administratively down, line protocol is down
Hardware is CPU Interface, address is 0001.43c6.07c2 (bia 0001.43c6.07c2)
MTU 1500 bytes, BW 100000 Kbit, DLY 1000000 usec,
reliability 255/255, txload 1/255, rxload 1/255
Encapsulation ARPA, loopback not set
ARP type: ARPA, ARP Timeout 04:00:00
Last input 21:40:21, output never, output hang never
Last clearing of "show interface" counters never
Input queue: 0/75/0/0 (size/max/drops/flushes); Total output drops: 0
Queueing strategy: fifo
Output queue: 0/40 (size/max)
5 minute input rate 0 bits/sec, 0 packets/sec
5 minute output rate 0 bits/sec, 0 packets/sec
1682 packets input, 530955 bytes, 0 no buffer
Received 0 broadcasts (0 IP multicast)
0 runts, 0 giants, 0 throttles
0 input errors, 0 CRC, 0 frame, 0 overrun, 0 ignored
563859 packets output, 0 bytes, 0 underruns
0 output errors, 23 interface resets
0 output buffer failures, 0 output buffers swapped out  
Вопросы:  
Назначен ли IP-адрес сети VLAN 1?  
нет  
Какой MAC-адрес имеет SVI? Возможны различные варианты ответов.  
address is 0001.43c6.07c2 (bia 0001.43c6.07c2)  
Данный интерфейс включен?  
нет  
>e.	Изучите IP-свойства интерфейса SVI сети VLAN 1.
>
Вопрос: Какие выходные данные вы видите?  
Switch>show ip interface vlan 1  
Vlan1 is administratively down, line protocol is down  
Internet protocol processing disabled

  2.Часть 2. Настройка базовых параметров сетевых устройств  
  >Топология сети
<img width="459" height="157" alt="image" src="https://github.com/user-attachments/assets/5e5a54c4-9087-4112-8e47-7f8c5f5a86d6" />

>Таблица адресации

| Устройства | Интерфейс | ip адрес/префикс | 
|------------|-----------|------------------|
|     S1     |   Vlan 1  |  192.168.1.2/24  |
|     PC-a   |    NIC    |  192.168.1.10/24 |

>Задаем пароль для консольного подключения

<img width="241" height="56" alt="image" src="https://github.com/user-attachments/assets/bc95eda5-0090-453a-8645-b2344f9ff6db" /> 

>Команда login включает доступ к привелигированному режиму EXEC
>В связи с тем что команда **paswword** хранит пароль в открытом виде выполним другую команду, которая позволяет хранить пароль в шифрованном виде

<img width="444" height="97" alt="image" src="https://github.com/user-attachments/assets/4944d8c0-22d1-44c6-a34e-37c24dbe115f" />


>b.	Назначьте IP-адрес интерфейсу SVI на коммутаторе. Благодаря этому вы получите возможность удаленного управления коммутатором.

Решение  
Switch(config-if)#ip address 192.168.1.2 255.255.255.0  
Switch(config-if)#  
>d.	Настройте каналы виртуального соединения для удаленного управления (vty), чтобы коммутатор разрешил доступ через Telnet. Если не настроить пароль VTY, будет невозможно подключиться к коммутатору по протоколу Telnet.

Switch(config)#line vty 04  
Switch(config-line)#transport input telnet 
>Настройте IP-адрес на компьютере PC-A

<img width="623" height="604" alt="image" src="https://github.com/user-attachments/assets/ab8c3a18-8c1e-4dd2-8561-2168771ac9ba"/>

>Протестируйте сквозное соединение, отправив эхо-запрос.

<img width="410" height="386" alt="image" src="https://github.com/user-attachments/assets/e7df24d4-e70c-479f-8897-5596f4a5b149" />

>Проверьте удаленное управление коммутатором S1

<img width="392" height="155" alt="image" src="https://github.com/user-attachments/assets/c498b114-06bd-4599-b529-b68dd341c042" />






  

