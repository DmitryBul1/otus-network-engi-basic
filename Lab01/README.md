# Лабораторная работа 1. Базовая настройка коммутатора
### Часть 1. Проверка конфигурации коммутатора по умолчанию
![image](https://user-images.githubusercontent.com/89464074/130942113-250fed32-8819-427a-a255-19f1be4504f9.png)

Производим первоначальное подключение к коммутатору через консоль, так как на коммутаторе не настроен VLAN и нет IP адреса для удаленного подключения по Telnet или Secure Shell.

![image](https://user-images.githubusercontent.com/89464074/130936390-29c9cf32-752c-49db-9db9-725252886d87.png)   ![image](https://user-images.githubusercontent.com/89464074/130936497-b3da0f56-bf36-4db5-b9f8-295a383d2580.png) 

Анализируя файл запущенной конфигурации, можно отметить:
- коммутатор имеет 24 порта FastEthernet и 2 порта GigabitEhernet; 
- диапазоны значений VTY-линий от 0 до 4 и от 5 до 15.

В памяти NVRAM нет сохраненной конфигурации, о чем говорит результат выполнения команды **show startup-config**
![image](https://user-images.githubusercontent.com/89464074/130937844-e75fa5cd-2724-44cb-8c06-023d60f2660e.png)

Рассмотрим виртуальный интерфейс для VLAN при помощи команды **show interface vlan1**:

![image](https://user-images.githubusercontent.com/89464074/130939269-f2d5c2df-56be-41d3-bf1f-0f343a17069b.png)

Интерфейс VLAN отключен, можно посмотреть MAC-адрес: **0001.c934.44bc**.

Подключаем Ethernet кабель компьютера к порту 6 коммутатора.

![image](https://user-images.githubusercontent.com/89464074/130943036-92f8262a-9bc5-47ec-ac6f-c1d7a2d5ad80.png) ![image](https://user-images.githubusercontent.com/89464074/130943181-9a95c599-4be2-4143-8260-88dcd6955f99.png)

Интерфейс FE0/6 стал активным.
Изучаем сведения о версии Cisco IOS на коммутаторе при помощи команды **show version**:

![image](https://user-images.githubusercontent.com/89464074/130944479-d11958ba-31aa-463e-abbe-50b824737509.png)

- коммутатор работает под управлением ОС версии **15.0(2)SE4**;
- файл образа системы называется **"c2960-lanbasek9-mz.150-2.SE4.bin"**;
- базовый MAC-адрес коммутатора **00:17:59:A7:51:80**.

Изучаем свойства по умолчанию интерфейса FastEthernet, который используется компьютером PC-A.
![image](https://user-images.githubusercontent.com/89464074/130945404-f484f6b9-ddf7-4b27-bbfc-2cd8aa5201f8.png)

- Интерфейс включен _(FastEthernet0/6 is up, line protocol is up (connected))_;
- Включение интерфейса осуществляется командой **no shutdown** в режиме конфигурации интерфейса;
- рассматриваемый интерфейс имеет MAC-адрес **00d0.581d.aa06**
- настройки скорости и дуплекса, заданные в интерфесе, **100Mb/s и Full-duplex** соответсвенно. 

Изучаем параметры сети VLAN по-умолчанию:

![image](https://user-images.githubusercontent.com/89464074/130947392-b558e70f-c872-45e9-9559-48222bdbb87c.png)

- Имя сети VLAN, присвоеннное по-умолчанию - **default**;
- порты, расположенные в сети VLAN: **от f0/1 до f0/24 для FastEthernet, и Gig0/1, Gig0/2 для GigabitEthernet**;
- сеть VLAN имеет статус **active**;
- сеть VLAN по-умолчаниею относится к типу **Default VLAN**.

Изучаем Flash-память коммутатора:

![image](https://user-images.githubusercontent.com/89464074/130949280-6373da71-8f78-4625-acfc-925ae96e2cc7.png)

В памяти находится только образ операционной системы с именем **2960-lanbasek9-mz.150-2.SE4.bin**


### Часть 2. Создание сети и настройка основных параметров устройства
Настроим базовые параметры коммутатора:

![image](https://user-images.githubusercontent.com/89464074/130952047-3f1bdb15-ba6b-4824-818a-c0f6bc6a7a39.png)

Назначим IP-адрес виртуальному интерфейсу для удаленного управления коммутатором:

![image](https://user-images.githubusercontent.com/89464074/130952617-4c35f2a6-c8c0-4f0a-ba31-27e4216696af.png)

Ограничим доступ через порт консоли:

![image](https://user-images.githubusercontent.com/89464074/130952946-4a2c7fbc-1fe2-43e5-a488-63524b238563.png)

Настроим каналы VTY для удаленного управления:

![image](https://user-images.githubusercontent.com/89464074/130953421-e65c4177-c713-403d-a502-d00ae47d34e7.png)

Настроим IP-адрес на компьютере PC-A:

![image](https://user-images.githubusercontent.com/89464074/130953544-ffd17e5e-f18b-4dd8-b4db-1b7813d8f79b.png)

### Часть 3. Проверка сетевых подключений
Используя консольное подключение на компьютере PC-A, отобразим и проверим конфигурацию коммутатора:

![image](https://user-images.githubusercontent.com/89464074/130954382-61b18951-e2b8-4027-a657-5ebbca448ebf.png) ![image](https://user-images.githubusercontent.com/89464074/130954609-8350a4dc-1f35-4219-8ec3-da89f4b25910.png)




- Отобразите конфигурацию устройства.
- Протестируйте сквозное соединение, отправив эхо-запрос.
- Протестируйте возможности удаленного управления с помощью Telnet.


