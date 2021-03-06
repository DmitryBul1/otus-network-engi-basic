# Лабораторная работа 5. Доступ к сетевым устройствам по протоколу SSH

### Топология по заданию:

![image](https://user-images.githubusercontent.com/89464074/174649685-aebf9ece-25a9-47bb-842f-3ed0fd55f3c4.png)

### Часть 1. Настройка основных параметров устройств

- Первоначальная настройка роутера R1 с отключением поиска DNS, защитой консоли и линий VTY, а также с шифрованием паролей и прописью баннера:

![image](https://user-images.githubusercontent.com/89464074/174728884-2f065603-02ff-4766-a4aa-382c1f498d7b.png)
![0174652626-c385b1f6-9f5b-4eee-bdf5-bdcb7dcf766f](https://user-images.githubusercontent.com/89464074/174728927-8bba9fc0-3ac4-44f2-8a3a-6e9364514998.png)

- Настроим и активируем интерфейс роутера G/0/01:

![image](https://user-images.githubusercontent.com/89464074/174654784-3d5737fc-e716-4cc7-90d7-057130c92e99.png)

- Настройка PC-A по исходным данным таблицы адресации и пробный эхо-запрос на шлюз:

![image](https://user-images.githubusercontent.com/89464074/174656165-cea4d746-a596-45ec-9351-eb77a36cadbf.png)

### Часть 2. Настройка маршрутизатора для доступа по протоколу SSH

- Указываем имя устройства и домен, создаем пользователя, создаем ключи шифрования:

![image](https://user-images.githubusercontent.com/89464074/174658032-380deeb7-53af-4ad3-a27b-d953f0a86894.png)

- Активируем протокол SSH на линиях VTY и сохраняем конфиг:

![image](https://user-images.githubusercontent.com/89464074/174730939-0eabb84b-5fcf-480a-b511-7563c3ad9635.png)

- Тестируем подключение с PC-A:

![image](https://user-images.githubusercontent.com/89464074/174659150-907f0abb-30a4-459b-98b1-41daaee23852.png)
![image](https://user-images.githubusercontent.com/89464074/174659237-484db6f5-9d00-4ae2-b254-c6bc623d6c0a.png)

### Часть 3. Настройка коммутатора для доступа по протоколу SSH

- Настроим основные параметры коммутатора:

![image](https://user-images.githubusercontent.com/89464074/174660723-1e65bed6-a74a-4581-87c7-fb00246c9bf0.png)  ![image](https://user-images.githubusercontent.com/89464074/174660774-84a1c17f-d150-4b9e-aca9-7a0921e40774.png)

![image](https://user-images.githubusercontent.com/89464074/174661766-8d842d21-fc2b-4dbb-926b-2cd1120a172e.png)

- Поднимаем интерфейс vlan1 на коммутаторе и сохраняем конфигурацию:

![image](https://user-images.githubusercontent.com/89464074/174662149-2819da79-b459-4799-aa4c-c2b446701525.png)

- Устанавливаем ключи шифрования, создаем пользователя и активируем протоколы telnet и SSH на линиях VTY: 
![image](https://user-images.githubusercontent.com/89464074/174732407-853dac66-7f10-4ad2-a00b-eeedebfe8b22.png)
![image](https://user-images.githubusercontent.com/89464074/174732113-404a828d-cfb4-4c5c-8ccc-f1bf044a5bfa.png)

- Тестируем подключение к коммутатору:

![image](https://user-images.githubusercontent.com/89464074/174663642-7335f33c-f253-4ff2-a7da-7a82807cfaa2.png)

![image](https://user-images.githubusercontent.com/89464074/174667905-8a4117d4-9f37-42d0-a897-7722306a61e6.png)


### Часть 4. Настройка протокола SSH с использованием интерфейса командной строки (CLI) коммутатора

- Подключаемся к роутеру R1 по SSH и тестируем элементы управления по заданию:

![image](https://user-images.githubusercontent.com/89464074/174733311-d4cd2643-73e6-4b37-af0c-1f081db0842f.png)

При использовании протокола SSH в устройствах Cisco доступны версии 1 и 2.

Пользователи создаются командой username, свойство privilege задает уровень привилегий для пользователя.









