# Лабораторная работа. Настройка и проверка расширенных списков контроля доступа
<img width="726" height="303" alt="image" src="https://github.com/user-attachments/assets/568a9e84-0a9b-4d41-aa35-e01d35227443" />  
<img width="757" height="412" alt="image" src="https://github.com/user-attachments/assets/d5159a07-1878-4b13-8f10-45eae6ebcaf6" />
<img width="740" height="241" alt="image" src="https://github.com/user-attachments/assets/e43fe237-abe1-43f4-ab95-29ef7e091fe9" /> 

## Часть 1. Создание сети и настройка основных параметров устройства
### Шаг 2. Произведите базовую настройку маршрутизаторов  

### a.	Назначьте маршрутизатору имя устройства.
### b.	Отключите поиск DNS, чтобы предотвратить попытки маршрутизатора неверно преобразовывать введенные команды таким образом, как будто они являются именами узлов.
### c.	Назначьте class в качестве зашифрованного пароля привилегированного режима EXEC.
### d.	Назначьте cisco в качестве пароля консоли и включите вход в систему по паролю.
### e.	Назначьте cisco в качестве пароля VTY и включите вход в систему по паролю.
### f.	Зашифруйте открытые пароли.
### g.	Создайте баннер с предупреждением о запрете несанкционированного доступа к устройству.
### h.	Сохраните текущую конфигурацию в файл загрузочной конфигурации.
<img width="537" height="340" alt="image" src="https://github.com/user-attachments/assets/35a66fcb-6caa-4831-85c5-281bc5870bc6" />

## Шаг 3. Настройте базовые параметры каждого коммутатора.
### a.	Присвойте коммутатору имя устройства.
### b.	Отключите поиск DNS, чтобы предотвратить попытки маршрутизатора неверно преобразовывать введенные команды таким образом, как будто они являются именами узлов.
### c.	Назначьте class в качестве зашифрованного пароля привилегированного режима EXEC.
### d.	Назначьте cisco в качестве пароля консоли и включите вход в систему по паролю.
### e.	Назначьте cisco в качестве пароля VTY и включите вход в систему по паролю.
### f.	Зашифруйте открытые пароли.
### g.	Создайте баннер с предупреждением о запрете несанкционированного доступа к устройству.
### h.	Сохраните текущую конфигурацию в файл загрузочной конфигурации.
<img width="499" height="306" alt="image" src="https://github.com/user-attachments/assets/1c4e833e-4e4e-4d45-ab58-bde8af6d326d" />

## Часть 2. Настройка сетей VLAN на коммутаторах.
### Шаг 1. Создайте сети VLAN на коммутаторах.

### a.	Создайте необходимые VLAN и назовите их на каждом коммутаторе из приведенной выше таблицы.
### b.	Настройте интерфейс управления и шлюз по умолчанию на каждом коммутаторе, используя информацию об IP-адресе в таблице адресации. 
### c.	Назначьте все неиспользуемые порты коммутатора VLAN Parking Lot, настройте их для статического режима доступа и административно деактивируйте их.
Примечание. Команда interface range полезна для выполнения этой задачи с помощью необходимого количества команд. 
<img width="538" height="327" alt="image" src="https://github.com/user-attachments/assets/5e7409fa-1e92-40cb-9133-e1b89769f18b" />
<img width="572" height="232" alt="image" src="https://github.com/user-attachments/assets/b92c26ca-1a13-4c53-bf31-2de6a33d81d0" />

## Шаг 2. Назначьте сети VLAN соответствующим интерфейсам коммутатора.
### a.	Назначьте используемые порты соответствующей VLAN (указанной в таблице VLAN выше) и настройте их для режима статического доступа.
<img width="377" height="51" alt="image" src="https://github.com/user-attachments/assets/0929617b-23ec-467c-8274-450e214db445" />
<img width="511" height="128" alt="image" src="https://github.com/user-attachments/assets/622300e5-31c3-40f6-95ab-517f5bce76b1" />

### b.	Выполните команду show vlan brief, чтобы убедиться, что сети VLAN назначены правильным интерфейсам.
<img width="631" height="263" alt="image" src="https://github.com/user-attachments/assets/a9a8d1a1-e76d-4495-ad3e-e1ef6ec9c70e" />
<img width="633" height="274" alt="image" src="https://github.com/user-attachments/assets/c5efcfac-d3bb-4303-854a-286873f2427f" />

# Часть3 Настройте транки (магистральные каналы)
### Шаг 1. Вручную настройте магистральный интерфейс F0/1.

#### a.	Измените режим порта коммутатора на интерфейсе F0/1, чтобы принудительно создать магистральную связь. Не забудьте сделать это на обоих коммутаторах.
#### b.	В рамках конфигурации транка установите для native vlan значение 1000 на обоих коммутаторах. При настройке двух интерфейсов для разных собственных VLAN сообщения об ошибках могут отображаться временно.
#### c.	В качестве другой части конфигурации транка укажите, что VLAN 10, 20, 30 и 1000 разрешены в транке.
#### d.	Выполните команду show interfaces trunk для проверки портов магистрали, собственной VLAN и разрешенных VLAN через магистраль.
<img width="478" height="111" alt="image" src="https://github.com/user-attachments/assets/91e0acc1-1ed0-47cc-ba39-3c278f8327d4" />
<img width="527" height="145" alt="image" src="https://github.com/user-attachments/assets/f84fe8ac-3f1e-4017-823f-4ca14f4a6229" />
<img width="593" height="206" alt="image" src="https://github.com/user-attachments/assets/679d33e7-dafa-45e9-9bea-37ef22f3b9fd" />
<img width="548" height="199" alt="image" src="https://github.com/user-attachments/assets/ee9741b0-1684-4502-9e2c-57a1789174e2" />

### Шаг 2. Вручную настройте магистральный интерфейс F0/5 на коммутаторе S1.
a.	Настройте интерфейс S1 F0/5 с теми же параметрами транка, что и F0/1. Это транк до маршрутизатора.
b.	Сохраните текущую конфигурацию в файл загрузочной конфигурации.
c.	Используйте команду show interfaces trunk для проверки настроек транка.
<img width="489" height="88" alt="image" src="https://github.com/user-attachments/assets/dcc05ee3-e7fe-4688-8ccf-3dff20fdace5" />
<img width="567" height="267" alt="image" src="https://github.com/user-attachments/assets/c2c4380d-2649-4b8a-b98d-9e4b94afa6de" />

### Шаг 1. Настройка маршрутизации между сетями VLAN на R1.
#### a.	Активируйте интерфейс G0/0/1 на маршрутизаторе.
#### b.	Настройте подинтерфейсы для каждой VLAN, как указано в таблице IP-адресации. Все подинтерфейсы используют инкапсуляцию 802.1Q. Убедитесь, что подинтерфейс для собственной VLAN не имеет назначенного IP-адреса. Включите описание для каждого подинтерфейса.
#### c.	Настройте интерфейс Loopback 1 на R1 с адресацией из приведенной выше таблицы.
#### d.	С помощью команды show ip interface brief проверьте конфигурацию подынтерфейса
<img width="603" height="376" alt="image" src="https://github.com/user-attachments/assets/5afd7eeb-a0f7-4c79-96b2-2add0bd811f5" />
<img width="641" height="164" alt="image" src="https://github.com/user-attachments/assets/f109eed4-364c-42d3-9c67-2ec1a7dccd10" />
<img width="623" height="166" alt="image" src="https://github.com/user-attachments/assets/54bff207-303b-49f3-9bf8-fd3f82c802a2" />

#### Шаг 2. Настройка интерфейса R2 g0/0/1 с использованием адреса из таблицы и маршрута по умолчанию с адресом следующего перехода 10.20.0.1
<img width="472" height="68" alt="image" src="https://github.com/user-attachments/assets/949dd137-bd01-48a5-b895-efced54da5af" />

### Часть 5. Настройте удаленный доступ
#### Шаг 1. Настройте все сетевые устройства для базовой поддержки SSH.
#### a.	Создайте локального пользователя с именем пользователя SSHadmin и зашифрованным паролем $cisco123!
#### b.	Используйте ccna-lab.com в качестве доменного имени.
#### c.	Генерируйте криптоключи с помощью 1024 битного модуля.
#### d.	Настройте первые пять линий VTY на каждом устройстве, чтобы поддерживать только SSH-соединения и с локальной аутентификацией.

<img width="595" height="327" alt="image" src="https://github.com/user-attachments/assets/e8f99d71-5e28-49c1-b671-eea05096c2b9" />
<img width="578" height="223" alt="image" src="https://github.com/user-attachments/assets/a90a708c-4b68-4c48-a5c7-d301657c832e" /> 

<img width="701" height="331" alt="image" src="https://github.com/user-attachments/assets/03674d75-e397-49b9-b8b9-8f17109a7b5b" />  
<img width="455" height="218" alt="image" src="https://github.com/user-attachments/assets/09985be2-6408-45a0-b30e-3cd664e7d17c" />  
<img width="460" height="221" alt="image" src="https://github.com/user-attachments/assets/76dbb3b7-ba6e-40ff-8adb-0f84b34032d5" />  
<img width="463" height="224" alt="image" src="https://github.com/user-attachments/assets/0861a78a-8216-43e6-92bf-bbae800558d7" />
<img width="457" height="215" alt="image" src="https://github.com/user-attachments/assets/a906119c-16a1-41eb-a50e-d46827d26b2c" />
<img width="458" height="215" alt="image" src="https://github.com/user-attachments/assets/0ca2554d-88ed-49e1-bf59-6190530d4a84" />
<img width="678" height="87" alt="image" src="https://github.com/user-attachments/assets/a1472941-5e5e-4c6f-ac94-affd9413e8b4" />
<img width="677" height="95" alt="image" src="https://github.com/user-attachments/assets/5d85564a-2ee2-46b6-b194-e5e893adf327" />
<img width="651" height="135" alt="image" src="https://github.com/user-attachments/assets/3de849f8-5139-4276-84c7-363ed9e8c2e6" />
<img width="652" height="150" alt="image" src="https://github.com/user-attachments/assets/16427217-281f-48d7-8cf4-fb74da031c14" />
<img width="658" height="169" alt="image" src="https://github.com/user-attachments/assets/e72d1b11-5738-4ff4-ae23-5e8be3107fb5" />
<img width="334" height="177" alt="image" src="https://github.com/user-attachments/assets/6a3cfd0f-7d9e-4e1b-803d-fbc78a8a2095" />

### Часть 7. Настройка и проверка списков контроля доступа (ACL)

 ##### Обединеные политики с 1-3 + требования ограничения доступа ко всем (кроме лупбек) интерфейсам роутера по 80 и 443 портам

<img width="463" height="181" alt="image" src="https://github.com/user-attachments/assets/22f2b8eb-2565-429f-b3a8-e5b35a53147d" />



### Политика 4: Cеть Operations  не может отправлять ICMP эхозапросы в сеть Sales. Разрешены эхо-запросы ICMP к другим адресатам. 
<img width="426" height="102" alt="image" src="https://github.com/user-attachments/assets/ec64b558-40cf-44f4-bda5-3aab8a11c5dc" />

<img width="911" height="390" alt="image" src="https://github.com/user-attachments/assets/94fd17d7-44fc-4676-bb48-e288f71d3229" />

<img width="484" height="402" alt="image" src="https://github.com/user-attachments/assets/5f9c73e8-2495-4360-a865-f47fefe9c88e" />

<img width="495" height="382" alt="image" src="https://github.com/user-attachments/assets/6af35764-b2e3-4f1e-8d4d-8c2543e77701" />

<img width="661" height="167" alt="image" src="https://github.com/user-attachments/assets/c38dbd28-f98b-4d12-942f-e64a1153ecd5" />

<img width="276" height="133" alt="image" src="https://github.com/user-attachments/assets/ac095a58-5f63-4fa3-827c-170ed44e3cd9" />












































