# Лабораторная работа - Конфигурация безопасности коммутатора
<img width="646" height="374" alt="image" src="https://github.com/user-attachments/assets/b3f6966f-9e7c-4024-a83a-fd7264cf158e" />  
<img width="712" height="240" alt="image" src="https://github.com/user-attachments/assets/f3ff2845-cdbf-4167-850b-b44b2167d88e" />  
## Часть 2. Настройка сетей VLAN на коммутаторах.
### Шаг 1. Сконфигруриуйте VLAN 10.
Добавьте VLAN 10 на S1 и S2 и назовите VLAN - Management.  
<img width="324" height="116" alt="image" src="https://github.com/user-attachments/assets/fe23d9bc-e780-4ec9-8704-a67ee1766fc3" />  
### Шаг 2. Сконфигруриуйте SVI для VLAN 10.

Настройте IP-адрес в соответствии с таблицей адресации для SVI для VLAN 10 на S1 и S2. Включите интерфейсы SVI и предоставьте описание для интерфейса.

S1(config)#interface vlan 10
S1(config-if)#ip address 192.168.10.201 255.255.255.0
S1(config-if)#description Management SVI
S1(config-if)#no shutdown





