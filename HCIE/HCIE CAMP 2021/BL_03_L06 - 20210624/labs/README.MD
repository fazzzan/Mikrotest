20210619

Оглавление HCIE-R&S+Lab+Guide+v3.0.pdf - стр. 05

Лабораторки 11

___ЛР11___
стр. 202 HCIE-R&S+Lab+Guide+v3.0.pdf

Дизайн, Адресация - на картинках ниже.

![](pictures/01.jpg)
![](pictures/02.jpg)
![](pictures/03.jpg)


## ЗАДАНИЕ ##
1. Настроить IP на всех IF R и сконфигурировать unicast routing протокол. 
2. Включить multicast на всех роутерах, PIM-SM на каждом IF, и IGMP на IF к которому подключен хост. 
3. Сконфигурировать одинаковый статический IP RP адрес на всех R. 
4. Сконфигурировать SPT switchover на Router C. 

## Решение ##

Настройка IF, OSPF - все просто

Вторая часть

Вкл Multicast, PIM-SM на каждом IF а на ACCESS порту - еще и IGMP
```
multicast routing-enable 
interface GigabitEthernet 0/0/1 
pim sm 
quit 

interface GigabitEthernet 0/0/2 
pim sm 
quit 

interface GigabitEthernet 0/0/3
pim sm 
igmp enable
quit 

display pim neighbor 
```


Configure a static RP on Router A, Router B, and Router C

```
pim 
static-rp 192.168.1.1 
quit 
```

Вывод об отказоустойчивости. после отключения IF 0/0/2 на RB
![](pictures/06.jpg)


Конфиги по задаче тут: 
[RouterA](config/L11/RouterA.txt), 
[RouterB](config/L11/RouterB.txt), 
[RouterC](config/L11/RouterC.txt)


___ЛР12___
стр. 221 HCIE-R&S+Lab+Guide+v3.0.pdf

Дизайн, Адресация - на картинках ниже.

![](pictures/07.jpg)
![](pictures/08.jpg)
![](pictures/09.jpg)


## ЗАДАНИЕ ##
1. Настроить IP для каждого IF R и настроить unicast routing protocol. PIM - intra-domain multicast routing protocol that depends on unicast routing protocols. 
2. Включить multicast на всех multicast R. перед настройкой PIM-SM, необходимо enable multicast. 
3. Включить PIM-SM на всех IF multicast роутеров. Сконфигурировать другие 
PIM-SM функции можно будет только после PIM-SM активации. 
4. Включить IGMP на IF подключенном к hosts, и переведите IGMP версию 
к IGMPv3. Получатель может подключиться и отключиться к multicast group определенного источника отправив специальное сообщение IGMP. Роутеры leaf (См/ leaf-spine) поддерживают отношения multicast member посредством IGMP. 
5. Задайте SSM групповой диапазон на всех роутерах, так чтобы multicast routers в PIM-SM домене предоставляли сервис для multicast groups в диапазоне адресов SSM. 

## Решение ##




Конфиги по задаче тут: 
[R1](config/L12/R1.txt), 
[R2](config/L12/R2.txt), 
[SW1](config/L12/SW1.txt), 
[SW2](config/L12/SW2.txt), 
[SW3](config/L12/SW3.txt)




___ЛР13___
стр. 253 HCIE-R&S+Lab+Guide+v3.0.pdf

Дизайн, Адресация - на картинках ниже.

![](pictures/10.jpg)
![](pictures/11.jpg)
![](pictures/12.jpg)


## ЗАДАНИЕ ##
1. Настроить IPv6 на всех IF. 
2. Настроить IS-ISv6 на R1, R2, R3, R4 и R5 для глобальной IPv6 связности. 
3. Включить IPv6 MC на всех R задействованных в MC. 
4. Включить IPv6 PIM-SM на всех IF роутеров, задействованных в MC. IPv6 PIM-SM функционал включится только после активации IPv6 PIM-SM. 
5. Включите MLD на IF R через которых подключены хосты и сконфигурируйте IF на статический join к MC группе. Получатель joins и leaves MC группу отправляя MLD сообщение. leaf routers поддерживают MC членство посредством MLD. 
6. Настройте RP. В IPv6 PIM-SM domain, RP is essential in providing ASM services и помогает транслировать MC данные. Настраивать RP рекомендуется на R у которого максимальное числа MC branches. Например, настройте R5 как RP сети. 

## Решение ##




Конфиги по задаче тут: 
[R1](config/L12/R1.txt), 
[R2](config/L12/R2.txt), 
[SW1](config/L12/SW1.txt), 
[SW2](config/L12/SW2.txt), 
[SW3](config/L12/SW3.txt)
