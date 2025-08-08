#**Лабораторная работа. Базовая настройка коммутатора**

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


  

