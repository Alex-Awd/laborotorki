# Лабораторная работа - Реализация DHCPv4 
<img width="758" height="516" alt="image" src="https://github.com/user-attachments/assets/9b4cd3e7-df16-4539-b68f-4a955139c760" />  

# Шаг 4.	Настройка маршрутизации между сетями VLAN на маршрутизаторе R1
### a.	Активируйте интерфейс G0/0/1 на маршрутизаторе.
<img width="261" height="50" alt="image" src="https://github.com/user-attachments/assets/38babd1f-123a-45de-88f0-ceefe5d9ab0f" />

### b.	Настройте подинтерфейсы для каждой VLAN в соответствии с требованиями таблицы IP-адресации. Все субинтерфейсы используют инкапсуляцию 802.1Q и назначаются первый полезный адрес из вычисленного пула IP-адресов. Убедитесь, что подинтерфейсу для native VLAN не назначен IP-адрес. Включите описание для каждого подинтерфейса.
<img width="601" height="179" alt="image" src="https://github.com/user-attachments/assets/742d9180-6a30-43ef-afcd-75e341b1e48c" />

### c.	Убедитесь, что вспомогательные интерфейсы работают.  
<img width="625" height="152" alt="image" src="https://github.com/user-attachments/assets/aa018284-5e66-4a83-bf74-fd75ce4690c3" />  

# Шаг 5.	Настройте G0/1 на R2, затем G0/0/0 и статическую маршрутизацию для обоих маршрутизаторов
### a.	Настройте G0/0/1 на R2 с первым IP-адресом подсети C, рассчитанным ранее.
<img width="463" height="55" alt="image" src="https://github.com/user-attachments/assets/2683e9a2-1767-4b27-8abc-c1403251ed94" />

### b.	Настройте интерфейс G0/0/0 для каждого маршрутизатора на основе приведенной выше таблицы IP-адресации.
<img width="440" height="125" alt="image" src="https://github.com/user-attachments/assets/e9146ae2-c12e-47c0-abf4-93b9644a8d25" />

### c.	Настройте маршрут по умолчанию на каждом маршрутизаторе, указываемом на IP-адрес G0/0/0 на другом маршрутизаторе.
<img width="386" height="77" alt="image" src="https://github.com/user-attachments/assets/a784df66-2d10-4e57-b281-ea450f92c8a9" />

### d.	Убедитесь, что статическая маршрутизация работает с помощью пинга до адреса G0/0/1 R2 от R1.  
<img width="593" height="76" alt="image" src="https://github.com/user-attachments/assets/0c18f904-afaa-49b6-ab69-e859ef3bdda9" />  

# Шаг 7.	Создайте сети VLAN на коммутаторе S1.
Примечание. S2 настроен только с базовыми настройками. 
### a.	Создайте необходимые VLAN на коммутаторе 1 и присвойте им имена из приведенной выше таблицы.
<img width="509" height="227" alt="image" src="https://github.com/user-attachments/assets/051ad63f-538e-4e7a-915d-7cf91ff34082" />

### b.	Настройте и активируйте интерфейс управления на S1 (VLAN 200), используя второй IP-адрес из подсети, рассчитанный ранее. Кроме того установите шлюз по умолчанию на S1.
<img width="485" height="103" alt="image" src="https://github.com/user-attachments/assets/5968f740-5c44-4e86-a1b0-7976f3c1603a" />

### c.	Настройте и активируйте интерфейс управления на S2 (VLAN 1), используя второй IP-адрес из подсети, рассчитанный ранее. Кроме того, установите шлюз по умолчанию на S2
<img width="474" height="135" alt="image" src="https://github.com/user-attachments/assets/137d5449-3ce5-41bf-8e2d-5119c0eff92a" />

### d.	Назначьте все неиспользуемые порты S1 VLAN Parking_Lot, настройте их для статического режима доступа и административно деактивируйте их. На S2 административно деактивируйте все неиспользуемые порты.
<img width="514" height="77" alt="image" src="https://github.com/user-attachments/assets/632e1f42-327b-4cf9-af40-ff98e9cf148b" />
<img width="562" height="72" alt="image" src="https://github.com/user-attachments/assets/cb3b5bbe-d0af-4e65-a90a-b9773bd62172" />  

# Шаг 8.	Назначьте сети VLAN соответствующим интерфейсам коммутатора.
### a.	Назначьте используемые порты соответствующей VLAN (указанной в таблице VLAN выше) и настройте их для режима статического доступа.
<img width="425" height="83" alt="image" src="https://github.com/user-attachments/assets/2db7d4e8-4c63-4909-b601-e08bbfada53e" />

### b.	Убедитесь, что VLAN назначены на правильные интерфейсы.  
<img width="637" height="309" alt="image" src="https://github.com/user-attachments/assets/883a06ed-153f-4093-9d36-3661db4fbb59" />  

#cШаг 9.	Вручную настройте интерфейс S1 F0/5 в качестве транка 802.1Q.
### a. Измените режим порта коммутатора, чтобы принудительно создать магистральный канал.
<img width="299" height="38" alt="image" src="https://github.com/user-attachments/assets/4e3163ed-94f7-4699-b3fb-412bdaeba25e" />

### b.	В рамках конфигурации транка  установите для native  VLAN значение 1000.
### c.	В качестве другой части конфигурации магистрали укажите, что VLAN 100, 200 и 1000 могут проходить по транку.
<img width="502" height="139" alt="image" src="https://github.com/user-attachments/assets/0e9fadf9-003b-48da-863e-e1acec6dfc9c" />

### e.	Проверьте состояние транка.
<img width="623" height="224" alt="image" src="https://github.com/user-attachments/assets/29cf9cfd-abe3-4888-8a1a-703ef55166a5" /> 

# Шаг 1.	Настройте R1 с пулами DHCPv4 для двух поддерживаемых подсетей. Ниже приведен только пул DHCP для подсети A
### a.	Исключите первые пять используемых адресов из каждого пула адресов.
<img width="520" height="38" alt="image" src="https://github.com/user-attachments/assets/12ca1cbf-6094-4762-a593-77d09dc08953" />

### b.	Создайте пул DHCP (используйте уникальное имя для каждого пула).
### c.	Укажите сеть, поддерживающую этот DHCP-сервер.
### d.	В качестве имени домена укажите CCNA-lab.com.
### e.	Настройте соответствующий шлюз по умолчанию для каждого пула DHCP.
### f.	Настройте время аренды на 2 дня 12 часов и 30 минут.
<img width="496" height="99" alt="image" src="https://github.com/user-attachments/assets/e476e3bf-372b-4205-816a-73b5beba6cdc" />

### g.	Затем настройте второй пул DHCPv4, используя имя пула R2_Client_LAN и вычислите сеть, маршрутизатор по умолчанию, и используйте то же имя домена и время аренды, что и предыдущий пул DHCP.
<img width="528" height="97" alt="image" src="https://github.com/user-attachments/assets/959eb1a2-a9ba-40f7-96e5-f00a85b93e8d" />  

# Шаг 3.	Проверка конфигурации сервера DHCPv4
### a.	Чтобы просмотреть сведения о пуле, выполните команду show ip dhcp pool.
<img width="632" height="442" alt="image" src="https://github.com/user-attachments/assets/42476ac7-953c-4ead-aeeb-238f75e718bb" />

# Шаг 4.	Попытка получить IP-адрес от DHCP на PC-A
### a.	Из командной строки компьютера PC-A выполните команду ipconfig /all
<img width="632" height="442" alt="image" src="https://github.com/user-attachments/assets/12ad9cf6-2f91-4c34-87da-9496ad5852f1" /> 

### c.	Проверьте подключение с помощью пинга IP-адреса интерфейса R0 G0/0/1.
<img width="458" height="221" alt="image" src="https://github.com/user-attachments/assets/24fca59b-9a65-4542-87f6-6333baf64b84" />  

# Шаг 1.	Настройка R2 в качестве агента DHCP-ретрансляции для локальной сети на G0/0/1
### a.	Настройте команду ip helper-address на G0/0/1, указав IP-адрес G0/0/0 R1.
<img width="531" height="109" alt="image" src="https://github.com/user-attachments/assets/5835b5cf-faea-4c69-bc7b-389a7f73fc28" />


















