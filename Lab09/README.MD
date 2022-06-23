### Лабораторная работа9. Конфигурация безопасности коммутатора

# Топология

![image](https://user-images.githubusercontent.com/89464074/175300599-a117a12b-ffc0-4a94-bdc4-5b4e54e7f91a.png)

- Настройка роутера по инструкции задания

![image](https://user-images.githubusercontent.com/89464074/175353616-c451c2fb-f7fc-43fd-a418-bb19414b876e.png)

возникла ошибка при вводе директивы ip dhcp relay information trusted

![image](https://user-images.githubusercontent.com/89464074/175353761-f28b73a2-0ebe-4ce8-84b1-30bcf12d9d7a.png)


![image](https://user-images.githubusercontent.com/89464074/175290138-5ea59640-70de-41d8-bdc7-1584dc4794c9.png)


- Настройка коммутаторов S1 и S2, создание VLAN:
- Настроим коммутаторы S1 и S2, зададим имя и description для активных портов:
![image](https://user-images.githubusercontent.com/89464074/175304862-5bc8ceb7-5322-47e1-bcd1-00d99f4e1448.png)
![image](https://user-images.githubusercontent.com/89464074/175354974-2646f8e3-2828-4a07-82bd-a276d28a6579.png)

- Создадим VLAN 10 на S1 и S2, укажем IP-адрес (по таблице задания) и шлюз по-умолчанию:

![image](https://user-images.githubusercontent.com/89464074/175356680-72221ee6-451f-42dd-af0b-693d61a0b596.png)

(примечание - ошибка в адресе на S1, в процессе всплыло - исправлено)

- Создаем VLAN 333 и 999 коммутаторах S1 и S2

![image](https://user-images.githubusercontent.com/89464074/175360187-4beb0b6b-7da0-4c07-8fb9-09de7233194f.png)

###Настройки безопасности коммутатора.

- Релизация магистральных соединений 802.1Q.

![image](https://user-images.githubusercontent.com/89464074/175363417-c96dec9b-3da4-4d7a-bda7-75b781f15e56.png)
![image](https://user-images.githubusercontent.com/89464074/175363533-e2e45741-c2bc-445d-8be4-9b4abb9c7da1.png)

- Смотрим результат при помощи команды sh int trunk

![image](https://user-images.githubusercontent.com/89464074/175363996-5dd94f2f-708d-4ef2-9753-879239f6d4f8.png)

При помощи команды switchport nonegotiate на портах f0/1 коммутаторов S1 и S2 было отключено согласование DTP.

![image](https://user-images.githubusercontent.com/89464074/175366136-fa1453f3-7f71-4793-8275-5b61e1f513ad.png)

- Порты f0/5-6 коммутатора S1 и порт s0/18 коммутатора S2 привязываются к VLAN 10

![image](https://user-images.githubusercontent.com/89464074/175367552-07b616da-b947-4602-b8bd-c156ea2d1a45.png)

- Отключим неиспользуемые порты и поместим их в VLAN 999

![image](https://user-images.githubusercontent.com/89464074/175369276-be8f0d8e-c194-464d-8ed5-1e3edbc630c9.png)
![image](https://user-images.githubusercontent.com/89464074/175369491-d756e170-c856-44f1-b274-94568b6216a4.png)

- Настройка безопасности на интерфейсах F0/6 на S1 и F0/18 на S2
Результат команды show port-security interface f0/6  на S1 (защита отключена)

![image](https://user-images.githubusercontent.com/89464074/175371834-5575221c-545c-4c70-8a85-4161dfea078e.png)

- Включим защиту порта на F0 / 6 на S1 и порта f0/18 на S2 при помощи команды switchport port-security и укажем параметры

![image](https://user-images.githubusercontent.com/89464074/175383118-36089c39-7422-44e7-b05f-6fc9ca6a7ade.png)

![image](https://user-images.githubusercontent.com/89464074/175384890-990b7527-e13c-400c-9cb6-46b1627702f9.png)

![image](https://user-images.githubusercontent.com/89464074/175383719-d7e3ef90-363a-4e3a-b931-9945e69a2663.png)

(примечание - лишние маки это результат экспериментов с командами)

![image](https://user-images.githubusercontent.com/89464074/175383944-6c8fafbc-ba50-4d6c-aa8c-fffdb60d63c7.png)

- Активируем sticky для порта f0/18 на S2

![image](https://user-images.githubusercontent.com/89464074/175384293-7a7b3e33-8d37-480f-9b31-ac75957df93a.png)

- Активируем Snooping, snooping trust и limit rate

![image](https://user-images.githubusercontent.com/89464074/175387524-c8f726dd-c863-4cc6-8840-c0eb95df6c51.png)

(примечание - изначально установил и траст и лимит на f0/1, далее исправил)

![image](https://user-images.githubusercontent.com/89464074/175388780-d5b1ea9c-bf2a-471c-b76e-6974d6931bf4.png)

- Обновляем IP-адрес PC-B

![image](https://user-images.githubusercontent.com/89464074/175395591-e04f1b70-6369-43d0-972b-7b282559edcb.png)

- Смотрим результат команды show ip dhcp snooping binding 

![image](https://user-images.githubusercontent.com/89464074/175399028-b44dce43-0839-476c-a697-c9502cd62142.png)

- Реализация PortFast и BPDU Guard

На всех активных интерфейсах портов коммутаторов выполнили spanning-tree portfast. 
На порте f0/6 на S1 и на порте f0/18 на S2 выполнили команду spanning-tree bpduguard en.

Вопросы для повторения
1.	С точки зрения безопасности порта на S2, почему нет значения таймера для оставшегося возраста в минутах, когда было сконфигурировано динамическое обучение - sticky?
2.	Что касается безопасности порта на S2, если вы загружаете скрипт текущей конфигурации на S2, почему порту 18 на PC-B никогда не получит IP-адрес через DHCP?
3.	Что касается безопасности порта, в чем разница между типом абсолютного устаревания и типом устаревание по неактивности?






