# Лабораторная работа - Конфигурация безопасности коммутатора
<img width="646" height="374" alt="image" src="https://github.com/user-attachments/assets/b3f6966f-9e7c-4024-a83a-fd7264cf158e" />  
<img width="712" height="240" alt="image" src="https://github.com/user-attachments/assets/f3ff2845-cdbf-4167-850b-b44b2167d88e" />  
## Часть 2. Настройка сетей VLAN на коммутаторах.
### Шаг 1. Сконфигруриуйте VLAN 10.
Добавьте VLAN 10 на S1 и S2 и назовите VLAN - Management.  
<img width="324" height="116" alt="image" src="https://github.com/user-attachments/assets/fe23d9bc-e780-4ec9-8704-a67ee1766fc3" />  
### Шаг 2. Сконфигруриуйте SVI для VLAN 10.

Настройте IP-адрес в соответствии с таблицей адресации для SVI для VLAN 10 на S1 и S2. Включите интерфейсы SVI и предоставьте описание для интерфейса.  

<img width="489" height="116" alt="image" src="https://github.com/user-attachments/assets/077ad2c2-47ae-4a07-bcf8-27415624d8d1" />
<img width="490" height="117" alt="image" src="https://github.com/user-attachments/assets/cfb176f5-2f9c-4509-9c3f-8ae2b0864922" />  

### Шаг 3. Настройте VLAN 333 с именем Native на S1 и S2.  
<img width="248" height="100" alt="image" src="https://github.com/user-attachments/assets/0c876910-4095-41e8-8519-fd7717fdd1bc" />

### Шаг 4. Настройте VLAN 999 с именем ParkingLot на S1 и S2.  
<img width="269" height="106" alt="image" src="https://github.com/user-attachments/assets/41271831-23ea-4953-964a-a531df79f358" />  

## Часть 3. Настройки безопасности коммутатора.
### Шаг 1. Релизация магистральных соединений 802.1Q.
#### a.	Настройте все магистральные порты Fa0/1 на обоих коммутаторах для использования VLAN 333 в качестве native VLAN.  
<img width="380" height="119" alt="image" src="https://github.com/user-attachments/assets/06f22c63-47c0-4081-b0de-c1fea98b3bc9" />

#### b.	Убедитесь, что режим транкинга успешно настроен на всех коммутаторах.  
<img width="539" height="195" alt="image" src="https://github.com/user-attachments/assets/69f29242-97ea-434c-a474-87233d8b7952" />
<img width="550" height="197" alt="image" src="https://github.com/user-attachments/assets/155ecba2-e1df-4ddd-8add-e96eab2dbb6b" />  

#### c.	Отключить согласование DTP F0/1 на S1 и S2. 
<img width="308" height="76" alt="image" src="https://github.com/user-attachments/assets/830d1ad1-af32-4745-bbdb-7b3410462728" />  

#### d.	Проверьте с помощью команды show interfaces.
<img width="480" height="105" alt="image" src="https://github.com/user-attachments/assets/bcfe39f1-c7cf-40c9-9097-b93c645c9ca7" />

## Шаг 2. Настройка портов доступа
#### a.	На S1 настройте F0/5 и F0/6 в качестве портов доступа и свяжите их с VLAN 10.
#### b.	На S2 настройте порт доступа Fa0/18 и свяжите его с VLAN 10.  
<img width="333" height="119" alt="image" src="https://github.com/user-attachments/assets/4551dcc9-bcdf-41b3-ba16-fadd2d9c7b4b" />  

## Шаг 3. Безопасность неиспользуемых портов коммутатора
#### a.	На S1 и S2 переместите неиспользуемые порты из VLAN 1 в VLAN 999 и отключите неиспользуемые порты.
<img width="463" height="164" alt="image" src="https://github.com/user-attachments/assets/0880f424-70e8-412c-861a-7a195b54bc55" />

#### b.	Убедитесь, что неиспользуемые порты отключены и связаны с VLAN 999, введя команду  show.
<img width="634" height="509" alt="image" src="https://github.com/user-attachments/assets/0757582f-8ed3-42f1-86a8-35a7b703c34a" />  
<img width="633" height="490" alt="image" src="https://github.com/user-attachments/assets/9b93a0e1-e3d9-467e-ad1f-df55584d67de" />  

## Шаг 4. Документирование и реализация функций безопасности порта.
#### a.	На S1, введите команду show port-security interface f0/6  для отображения настроек по умолчанию безопасности порта для интерфейса F0/6. Запишите свои ответы ниже.  
<img width="421" height="212" alt="image" src="https://github.com/user-attachments/assets/815fbd99-8fd3-40cb-ad9a-f79fcc8584bc" />  

#### b.	На S1 включите защиту порта на F0 / 6 со следующими настройками:
o	Максимальное количество записей MAC-адресов: 3
o	Режим безопасности: restrict
o	Aging time: 60 мин.
o	Aging type: неактивный  

<img width="533" height="181" alt="image" src="https://github.com/user-attachments/assets/d157483f-d276-4c04-ab2a-3d431d1949b6" />  

#### c.	Verify port security on S1 F0/6.
<img width="369" height="221" alt="image" src="https://github.com/user-attachments/assets/22b3d8ad-96d4-434d-b0f4-c3f5156d2b2a" />  
<img width="632" height="158" alt="image" src="https://github.com/user-attachments/assets/5ea92545-5b70-429f-a1ec-3e6bb26e67eb" />  

#### d.	Включите безопасность порта для F0 / 18 на S2. Настройте каждый активный порт доступа таким образом, чтобы он автоматически добавлял адреса МАС, изученные на этом порту, в текущую конфигурацию.  
<img width="478" height="61" alt="image" src="https://github.com/user-attachments/assets/28d6476b-ef36-4493-bb6b-0e1c324c45b9" />  

#### e.	Настройте следующие параметры безопасности порта на S2 F / 18:
#### o	Максимальное количество записей MAC-адресов: 2
#### o	Тип безопасности: Protect
#### o	Aging time: 60 мин.
<img width="473" height="78" alt="image" src="https://github.com/user-attachments/assets/2a2a3680-fffb-4286-af4b-3b823c033a4c" />

#### f.	Проверка функции безопасности портов на S2 F0/18.
<img width="388" height="219" alt="image" src="https://github.com/user-attachments/assets/9e458e33-6cb1-4fd8-b04a-b7385f6509bd" /> 
<img width="635" height="149" alt="image" src="https://github.com/user-attachments/assets/df0c9661-a81a-48eb-9790-ba3c40f06cfe" />  

## Шаг 5. Реализовать безопасность DHCP snooping.  

#### a.	На S2 включите DHCP snooping и настройте DHCP snooping во VLAN 10.  
<img width="305" height="42" alt="image" src="https://github.com/user-attachments/assets/53e05c9b-2df3-4d68-a966-ad25e0a74dfb" />

#### b.	Настройте магистральные порты на S2 как доверенные порты.
<img width="312" height="44" alt="image" src="https://github.com/user-attachments/assets/275cc36d-4181-445e-8417-c5666155ec43" />

#### c.	Ограничьте ненадежный порт Fa0/18 на S2 пятью DHCP-пакетами в секунду.
<img width="368" height="47" alt="image" src="https://github.com/user-attachments/assets/b8b8abad-bce4-4390-a48a-e59e1ecf5357" />

#### d.	Проверка DHCP Snooping на S2.  
<img width="454" height="179" alt="image" src="https://github.com/user-attachments/assets/d183e1ed-7505-408f-884f-5a4948fdf7dd" />  

### Шаг 6. Реализация PortFast и BPDU Guard  

#### a.	Настройте PortFast на всех портах доступа, которые используются на обоих коммутаторах.
<img width="598" height="260" alt="image" src="https://github.com/user-attachments/assets/cf1bf0a2-26bf-4c0c-abd0-3acef009f762" />  
<img width="598" height="182" alt="image" src="https://github.com/user-attachments/assets/3c9fc859-20fe-444a-b2b5-390052505757" />


#### b.	Включите защиту BPDU на портах доступа VLAN 10 S1 и S2, подключенных к PC-A и PC-B.
<img width="397" height="78" alt="image" src="https://github.com/user-attachments/assets/d5cb2109-d01a-4c5b-97c6-d4e136204d9d" />

#### c.	Убедитесь, что защита BPDU и PortFast включены на соответствующих портах.  
<img width="520" height="225" alt="image" src="https://github.com/user-attachments/assets/7c224037-3eea-4b6a-bc50-4e4bfeeb6710" />
































