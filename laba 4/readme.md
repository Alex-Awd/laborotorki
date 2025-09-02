# Лабораторная работа. Настройка IPv6-адресов на сетевых устройствах
## Топология  
<img width="636" height="124" alt="image" src="https://github.com/user-attachments/assets/4b7ef517-30c9-4f73-973e-71211dd49bdb" />  

### Таблица адресации  
<img width="742" height="205" alt="image" src="https://github.com/user-attachments/assets/bc5a5c07-b86c-4ce0-b503-d6433fc8dc13" />  

## Задачи
### Часть 1. Настройка топологии и конфигурация основных параметров маршрутизатора и коммутатора
### Часть 2. Ручная настройка IPv6-адресов
### Часть 3. Проверка сквозного соединения  

>Устанавливаем шаблон dual-ipv4-and-ipv6 в качестве шаблона SDM по умолчанию

<img width="617" height="211" alt="image" src="https://github.com/user-attachments/assets/5ac33e9d-940d-4dbf-986b-47e5f3a055c9" />  

## Шаг 1. Настройте маршрутизатор.
### Назначьте имя хоста и настройте основные параметры устройства.  
<img width="278" height="310" alt="image" src="https://github.com/user-attachments/assets/c1dd652b-1b0b-4fba-a65b-f401a0b9fced" />  

## Шаг 2. Настройте коммутатор.
### Назначьте имя хоста и настройте основные параметры устройства.  
<img width="460" height="266" alt="image" src="https://github.com/user-attachments/assets/787f05e6-afa6-4e79-bd40-c6bd4e668991" />  

# Часть 2. Ручная настройка IPv6-адресов  
## Шаг 1. Назначьте IPv6-адреса интерфейсам Ethernet на R1.  
### a.Назначьте глобальные индивидуальные IPv6-адреса, указанные в таблице адресации обоим интерфейсам Ethernet на R1  
<img width="636" height="316" alt="image" src="https://github.com/user-attachments/assets/e934aa86-008c-4b02-a40f-bc98e9b0c3d5" />  

### b.Ведите команду show ipv6 interface brief, чтобы проверить, назначен ли каждому интерфейсу корректный индивидуальный IPv6-адрес.  
<img width="448" height="149" alt="image" src="https://github.com/user-attachments/assets/f9bc3e79-0f6d-4bbb-a1fe-e88ba97d81ac" />  

### c.Чтобы обеспечить соответствие локальных адресов канала индивидуальному адресу, вручную введите локальные адреса канала на каждом интерфейсе Ethernet на R1.  
<img width="331" height="199" alt="image" src="https://github.com/user-attachments/assets/3147e540-7115-4cb5-bfb1-5c73f3016c85" />  

### d.Используйте выбранную команду, чтобы убедиться, что локальный адрес связи изменен на fe80::1.  
<img width="428" height="118" alt="image" src="https://github.com/user-attachments/assets/620489cd-cb14-49ed-8a6a-55fd6e0bec93" />  

>группы многоадресной рассылки назначены интерфейсу G0/0/0 отмечены желтым цветом

<img width="427" height="319" alt="image" src="https://github.com/user-attachments/assets/a2301ee1-e3fb-43b6-bf44-3620869f2fb6" />  

## Шаг 2. Активируйте IPv6-маршрутизацию на R1.  
### a.В командной строке на PC-B введите команду ipconfig, чтобы получить данные IPv6-адреса, назначенного интерфейсу ПК.  
<img width="471" height="179" alt="image" src="https://github.com/user-attachments/assets/087488bc-48eb-4e9a-a701-bc549b01d00c" />

Индивидуальный IPv6-адрес сетевой интерфейсной карте (NIC) на PC-B не назначен  
### b.Активируйте IPv6-маршрутизацию на R1 с помощью команды IPv6 unicast-routing.  
R1(config)#ipv6 unicast-routing  

R1(config)#  

### c.Теперь, когда R1 входит в группу многоадресной рассылки всех маршрутизаторов, еще раз введите команду ipconfig на PC-B. Проверьте данные IPv6-адреса.












