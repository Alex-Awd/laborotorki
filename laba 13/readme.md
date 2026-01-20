<img width="716" height="396" alt="image" src="https://github.com/user-attachments/assets/e8f30642-edfb-4456-b63c-12aac104ff78" />

## Шаг 2. Настройте базовые параметры для маршрутизатора.

<img width="513" height="407" alt="image" src="https://github.com/user-attachments/assets/0b69a13c-76cc-40fe-b9ff-2e87a7ddb68c" />

## Шаг 3. Настройте базовые параметры каждого коммутатора.
<img width="533" height="323" alt="image" src="https://github.com/user-attachments/assets/89ce6277-670f-42f6-862a-349f8e4406e8" />  

### Часть 2. Обнаружение сетевых ресурсов с помощью протокола CDP

#### a.	На R1 используйте соответствующую команду show cdp, чтобы определить, сколько интерфейсов включено CDP, сколько из них включено и сколько отключено.
 
###Вопрос:
#### Сколько интерфейсов участвует в объявлениях CDP? Какие из них активны?
#### Введите ваш ответ здесь.

<img width="403" height="82" alt="image" src="https://github.com/user-attachments/assets/12ea3ead-d111-4a9e-9991-d9da00bd737e" />

#### b.	На R1 используйте соответствующую команду show cdp, чтобы определить версию IOS, используемую на S1.
<img width="839" height="267" alt="image" src="https://github.com/user-attachments/assets/861041e4-da78-41d1-b25e-21a142aed07b" />

#### Какая версия IOS используется на  S1?
##### Version 15.0(2)SE4

##### c.	На S1 используйте соответствующую команду show cdp, чтобы определить, сколько пакетов CDP было выданных.
<img width="386" height="77" alt="image" src="https://github.com/user-attachments/assets/36292c82-4a97-4bab-a878-a6fc2dc11f9c" />

##### d.	Настройте SVI для VLAN 1 на S1 и S2, используя IP-адреса, указанные в таблице адресации выше. Настройте шлюз по умолчанию для каждого коммутатора на основе таблицы адресов  

<img width="319" height="282" alt="image" src="https://github.com/user-attachments/assets/f38342a6-861b-4ec6-a31a-b9cab3e525b4" />  

### e.	На R1 выполните команду show cdp entry S1 . 

<img width="624" height="296" alt="image" src="https://github.com/user-attachments/assets/e5c748c3-3432-4403-9efe-629d688d98bd" />

#### f.	Отключить CDP глобально на всех устройствах. 

<img width="207" height="58" alt="image" src="https://github.com/user-attachments/assets/60147f93-b94c-4d19-8528-e62842419d1f" />


#### Часть 3. Обнаружение сетевых ресурсов с помощью протокола LLDP

### a.	Введите соответствующую команду lldp, чтобы включить LLDP на всех устройствах в топологии.

<img width="192" height="67" alt="image" src="https://github.com/user-attachments/assets/2e840194-43b3-4f0d-830e-be5ec6d3a2d8" />

### b.	На S1 выполните соответствующую команду lldp, чтобы предоставить подробную информацию о S2. 

<img width="374" height="67" alt="image" src="https://github.com/user-attachments/assets/d89f4b22-122d-4c2d-ae42-ba98603b8ec6" />

#### Часть 4. Настройка NTP
##### Шаг 1. Выведите на экран текущее время.

<img width="294" height="39" alt="image" src="https://github.com/user-attachments/assets/8a8eefaf-6e14-4828-b0e1-c0d89c253aca" />  
#### Шаг 2. Установите время.

<img width="317" height="29" alt="image" src="https://github.com/user-attachments/assets/f9d85473-0ee5-4464-bb96-352b2865e75f" />

#### Шаг 3. Настройте главный сервер NTP.

<img width="203" height="24" alt="image" src="https://github.com/user-attachments/assets/2bd3b277-6aa4-4936-ab0a-5cab3fd487b9" />


#### Шаг 4. Настройте клиент NTP.
#### b.	Настройте S1 и S2 в качестве клиентов NTP. Используйте соответствующие команды NTP для получения времени от интерфейса G0/0/1 R1, а также для периодического обновления календаря или аппаратных часов коммутатора.

<img width="285" height="108" alt="image" src="https://github.com/user-attachments/assets/e9cbfcd0-2e33-4431-87a1-60f9c36eed5e" />

#### Шаг 5. Проверьте настройку NTP.

a.	Используйте соответствующую команду show , чтобы убедиться, что S1 и S2 синхронизированы с R1.
Примечание. Синхронизация метки времени на маршрутизаторе R2 с меткой времени на маршрутизаторе R1 может занять несколько минут.
b.	Выполните соответствующую команду на S1 и S2, чтобы просмотреть настроенное время и сравнить ранее записанное время.

<img width="354" height="50" alt="image" src="https://github.com/user-attachments/assets/117fb89d-f09e-4f98-95fe-d5893675919f" />








