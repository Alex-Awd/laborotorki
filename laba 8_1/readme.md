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








