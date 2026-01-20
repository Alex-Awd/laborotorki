<img width="684" height="291" alt="image" src="https://github.com/user-attachments/assets/6f235450-f4ea-455d-9413-e3c5d797fc63" />  
<img width="699" height="278" alt="image" src="https://github.com/user-attachments/assets/8ca3c818-cadd-4686-931d-785642f03e95" />

## Шаг 2. Произведите базовую настройку маршрутизаторов.

<img width="522" height="529" alt="image" src="https://github.com/user-attachments/assets/d016244c-9cdf-4da3-b759-169c9951f8a3" />
<img width="502" height="482" alt="image" src="https://github.com/user-attachments/assets/cd6ae207-6342-4b7b-95be-113a8ced5d55" />

## Шаг 3. Настройте базовые параметры каждого коммутатора.

<img width="508" height="463" alt="image" src="https://github.com/user-attachments/assets/45e7dc5e-1ebe-4a40-919a-e0feda11cde2" />  
<img width="531" height="448" alt="image" src="https://github.com/user-attachments/assets/54bfb849-043e-45ef-8366-40a5284e4a7f" />



# Часть 2. Настройка и проверка NAT для IPv4.  
## Шаг 1. Настройте NAT на R1, используя пул из трех адресов 209.165.200.226-209.165.200.228. 

### a.	Настройте простой список доступа, который определяет, какие хосты будут разрешены для трансляции. В этом случае все устройства в локальной сети R1 имеют право на трансляцию. 
### b.	Создайте пул NAT и укажите ему имя и диапазон используемых адресов.

### c.	Настройте перевод, связывая ACL и пул с процессом преобразования.
 
### d.	Задайте внутренний (inside) интерфейс. 

### e.	Определите внешний (outside) интерфейс.
<img width="637" height="223" alt="image" src="https://github.com/user-attachments/assets/ef73b766-d77a-4939-b021-51ac0b1a0c39" />

## Шаг 2. Проверьте и проверьте конфигурацию. 
### a.	С PC-B,  запустите эхо-запрос интерфейса Lo1 (209.165.200.1) на R2. Если эхо-запрос не прошел, выполните процес поиска и устранения неполадок. На R1 отобразите таблицу NAT на R1 с помощью команды show ip nat translations.

<img width="633" height="109" alt="image" src="https://github.com/user-attachments/assets/b90f6d9b-dc7e-4124-82c4-9a91a591abb2" />


#### Вопросы:
#### Во что был транслирован внутренний локальный адрес PC-B?
#### Введите ваш ответ здесь.
 ##### 209.165.200.226
#### Какой тип адреса NAT является переведенным адресом?

##### Inside Global
 
### b.	С PC-A, запустите  эхо-запрос интерфейса Lo1 (209.165.200.1) на R2. Если эхо-запрос не прошел, выполните отладку. На R1 отобразите таблицу NAT на R1 с помощью команды show ip nat translations.

<img width="471" height="226" alt="image" src="https://github.com/user-attachments/assets/5cfea437-4c6c-42e5-8612-d7f8894f5720" />


#### c.	Обратите внимание, что предыдущая трансляция для PC-B все еще находится в таблице. Из S1, эхо-запрос интерфейса Lo1 (209.165.200.1) на R2. Если эхо-запрос не прошел, выполните отладку. На R1 отобразите таблицу NAT на R1 с помощью команды show ip nat translations.

<img width="626" height="196" alt="image" src="https://github.com/user-attachments/assets/9ca4aa07-ea1e-4043-8906-bfad552084a4" />


#### d.	Теперь запускаем пинг R2 Lo1 из S2. На этот раз перевод завершается неудачей, и вы получаете эти сообщения (или аналогичные) на консоли R1:
Sep 23 15:43:55.562: %IOSXE-6-PLATFORM: R0/0: cpp_cp: QFP:0.0 Thread:000 TS:00000001473688385900 %NAT-6-ADDR_ALLOC_FAILURE: Address allocation failed; pool 1 may be exhausted [2]
e.	Это ожидаемый результат, потому что выделено только 3 адреса, и мы попытались ping Lo1 с четырех устройств. Напомним, что NAT — это трансляция «один-в-один». Как много выделено трансляций? Введите команду show ip nat translations verbose , и вы увидите, что ответ будет 24 часа.
R1# show ip nat translations verbose 
Pro Inside global Inside local Outside local Outside global
--- 209.165.200.226 192.168.1.3 --- ---
  create: 09/23/19 15:35:27, use: 09/23/19 15:35:27, timeout: 23:56:42
  Map-Id(In): 1
<output omitted>
#### f.	Учитывая, что пул ограничен тремя адресами, NAT для пула адресов недостаточно для нашего приложения. Очистите преобразование NAT и статистику, и мы перейдем к PAT.  

<img width="321" height="89" alt="image" src="https://github.com/user-attachments/assets/dc22c0fd-38de-4a75-b052-aca616b97b03" />





