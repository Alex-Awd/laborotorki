# Лабораторная работа. Настройка протокола OSPFv2 для одной области
<img width="732" height="357" alt="image" src="https://github.com/user-attachments/assets/a9dd0f5e-d033-492e-8552-bc3d9fee847f" />  

## Часть 2. Настройка и проверка базовой работы протокола OSPFv2 для одной области
### a.	Настройте адреса интерфейсов на каждом маршрутизаторе, как показано в таблице адресации выше.
<img width="452" height="200" alt="image" src="https://github.com/user-attachments/assets/12b7abb2-2cfa-4401-b480-b63a13f961aa" />  

### b.	Перейдите в режим конфигурации маршрутизатора OSPF, используя идентификатор процесса 56.  
### c.	Настройте статический идентификатор маршрутизатора для каждого маршрутизатора (1.1.1.1 для R1, 2.2.2.2 для R2).
### d.	Настройте инструкцию сети для сети между R1 и R2, поместив ее в область 0.  

<img width="309" height="164" alt="image" src="https://github.com/user-attachments/assets/c984b22a-7a71-4ea3-8f22-0f354479f01c" />  

### e.	Только на R2 добавьте конфигурацию, необходимую для объявления сети Loopback 1 в область OSPF 0.

<img width="272" height="36" alt="image" src="https://github.com/user-attachments/assets/92b50f0d-bc26-4c86-8e15-57c5259f0b1d" />  

### f.	Убедитесь, что OSPFv2 работает между маршрутизаторами. Выполните команду, чтобы убедиться, что R1 и R2 сформировали смежность.
<img width="608" height="342" alt="image" src="https://github.com/user-attachments/assets/d4055a92-94f8-46e3-886a-d680b9c61588" />
<img width="629" height="455" alt="image" src="https://github.com/user-attachments/assets/1c1974a7-c9a3-4b60-aa97-63386a097f6f" />

### g.	На R1 выполните команду show ip route ospf, чтобы убедиться, что сеть R2 Loopback1 присутствует в таблице маршрутизации. Обратите внимание, что поведение OSPF по умолчанию заключается в объявлении интерфейса обратной связи в качестве маршрута узла с использованием 32-битной маски.  
<img width="625" height="67" alt="image" src="https://github.com/user-attachments/assets/a2ac737a-6771-4528-afa4-1120260db0d5" /> 

### h.	Запустите Ping до  адреса интерфейса R2 Loopback 1 из R1. Выполнение команды ping должно быть успешным.
<img width="576" height="108" alt="image" src="https://github.com/user-attachments/assets/c8e62e71-0a08-4108-a6bc-8db732028544" /> 

# Часть 3. Оптимизация и проверка конфигурации OSPFv2 для одной области
## Шаг 1. Реализация различных оптимизаций на каждом маршрутизаторе.
### a.	На R1 настройте приоритет OSPF интерфейса G0/0/1 на 50, чтобы убедиться, что R1 является назначенным маршрутизатором.
<img width="604" height="386" alt="image" src="https://github.com/user-attachments/assets/835b0376-9dfb-405d-aba0-a8ce34702e06" /> 

### b.	Настройте таймеры OSPF на G0/0/1 каждого маршрутизатора для таймера приветствия, составляющего 30 секунд.  
<img width="345" height="50" alt="image" src="https://github.com/user-attachments/assets/8fa30906-f521-4a3c-ac34-dfe2768ceac7" />
<img width="353" height="62" alt="image" src="https://github.com/user-attachments/assets/82f167b0-e50b-466c-844d-67d1f83211a4" /> 

### c.	На R1 настройте статический маршрут по умолчанию, который использует интерфейс Loopback 1 в качестве интерфейса выхода. Затем распространите маршрут по умолчанию в OSPF. Обратите внимание на сообщение консоли после установки маршрута по умолчанию.
<img width="514" height="83" alt="image" src="https://github.com/user-attachments/assets/ae572bcf-415f-4820-8072-d68e626d8e33" /> 

### d.	добавьте конфигурацию, необходимую для OSPF для обработки R2 Loopback 1 как сети точка-точка. Это приводит к тому, что OSPF объявляет Loopback 1 использует маску подсети интерфейса.
<img width="414" height="38" alt="image" src="https://github.com/user-attachments/assets/dfa93bd3-bcac-4a0a-81ed-7f1e36433216" />

### e.	Только на R2 добавьте конфигурацию, необходимую для предотвращения отправки объявлений OSPF в сеть Loopback 1.  
<img width="407" height="54" alt="image" src="https://github.com/user-attachments/assets/48494986-5d2d-424d-b137-1d2423f50ade" />

### f.	Измените базовую пропускную способность для маршрутизаторов. После этой настройки перезапустите OSPF с помощью команды clear ip ospf process . Обратите внимание на сообщение консоли после установки новой опорной полосы пропускания.
<img width="610" height="70" alt="image" src="https://github.com/user-attachments/assets/3fef7ae8-31ae-45a9-afa1-fafae89739ca" />
<img width="616" height="68" alt="image" src="https://github.com/user-attachments/assets/ecdf16ab-d773-4dd1-9427-ce3baf0c3f49" />

## Шаг 2. Убедитесь, что оптимизация OSPFv2 реализовалась.

### a.	Выполните команду show ip ospf interface g0/0/1 на R1 и убедитесь, что приоритет интерфейса установлен равным 50, а временные интервалы — Hello 30, Dead 120, а тип сети по умолчанию — Broadcast
<img width="606" height="232" alt="image" src="https://github.com/user-attachments/assets/baa65893-7c86-42b4-ae54-18fe2d094eb8" />
  
### b.	На R1 выполните команду show ip route ospf, чтобы убедиться, что сеть R2 Loopback1 присутствует в таблице маршрутизации. Обратите внимание на разницу в метрике между этим выходным и предыдущим выходным. Также обратите внимание, что маска теперь составляет 24 бита, в отличие от 32 битов, ранее объявленных.  
<img width="587" height="54" alt="image" src="https://github.com/user-attachments/assets/3c60dfc6-6cc6-4745-b6ba-9ad0a12787f2" />  

### c.	Введите команду show ip route ospf на маршрутизаторе R2. Единственная информация о маршруте OSPF должна быть распространяемый по умолчанию маршрут R1.
<img width="567" height="53" alt="image" src="https://github.com/user-attachments/assets/a6e5f6e9-cb5d-4979-97be-2d785767c869" />  

### d.	Запустите Ping до адреса интерфейса R1 Loopback 1 из R2. Выполнение команды ping должно быть успешным.  
<img width="565" height="113" alt="image" src="https://github.com/user-attachments/assets/4ee0b26a-94d2-4149-bde2-b65f7c297092" />



















