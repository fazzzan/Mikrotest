20210621
# Route Import and Control #

https://support.huawei.com/enterprise/en/doc/EDOC1100055099/

Доп. материалы
03_L05++01_Traffic Filtering and Forwarding Path Control.pdf
03_L05++02_Routing Policy and Route Control.pdf
https://support.huawei.com/enterprise/en/doc/EDOC1100055099/527b9fb7/example-for-configuration-prefix-based-bgp-orf

___Материал 5-го дня___ 
- LAB GUIDE Л/Р 09 (145-183 / 00:27:00 - 00:29:13) 
- Route Import and Control  (487-561 / 02:46:00 - 05:26:00) (Имеет смысл прослушать перед OSPF (BL01_L02))
  - Route Filter (491-509 / 02:46:00 - 03:09:50)
     - ACL (491-498 / 02:49:49 - 02:56:07) - не фильтрация а классификатор сеток. которые зафильтруем позже или проконтроллируем при редистрибуции, используем базовые ACL. Negative Match - неявный deny. Номер ACL IPv4/IPv6 - не конфликтуют между собой
         - доп. 03_L05++03_HCIP-Routing & Switching-IERS V2.5 Training Materials.pdf (330-504 / 02:54:17 - 02:56:07) - почему не всегда подходит ACL и почему нужен IP Prefix List 
     - IP Prefix List (499-504 / 02:56:07 - 03:06:26) - Исключительно Control Plane ("стратегический" уровень). Более гибкие задачи, на матчинг по битам, в конце PrefL - неявный deny        
     - (BGP) 
        - AS-Path Filter (505-507 / 03:06:26 - 03:08:50) - регулярки (regular)
        - Community Filter  (508-509 / 03:08:50 - 03:09:50)
  - Routing policy and PBR (510-525 / 03:09:57 - 04:46:10)
     - Routing policy (511-518 / 03:09:57 - 03:25:42; 04:30:00 - 04:46:11; ) - машина фильтрации; 
         - доп. 03_L05++03_HCIP-Routing & Switching-IERS V2.5 Training Materials.pdf (357 / 03:16:47 - 03:20:00) 
         - OSPF
           - filter-policy import (515) (аналог Cisco distribute list) - топологическая информация не фильтруется: как роутер принимал, так и остается - влияет на контроль записи в таблицу маршрутизации;
           - filter-policy expport (515)
         - ISIS
            - filter-policy import (516)
            - filter-policy export (516)
         - BGP - Это DV протокол, поэтому уже тут можно повлиять на то, что принимаем/отправляем по пирингу или редистрибуции
            - filter-policy import (517)
            - filter-policy export (517)
     - PBR (519-523 / 04:46:11 - 04:57:00) - Речь про data-plane, возможность отправлять пакеты исходя из матчинга по пути указанному в PBR, в ensp - interface PBR не работает
         - доп. 03_L05++01_Traffic Filtering and Forwarding Path Control.pdf (5-17 / 04:50:00 - 04:55:00) - кратко посмотреть материал    
        - Local PBR - траф от самого роутера (521)
        - Interface PBR - траф, который вхордит в роутер (521)
        - Smart Policy Routing - направление движения исходя из качествапути (521)
     - Comparision Routing Policy & PBR (524-525 / 04:57:00 -  04:57:38)
  - Routing policy and PBR Config command (526-546 / 04:57:38 - 0X:XX:00)
     - Config route Import (527-534 / 04:57:38 - 05:05:49)
        - Direct Route Import (527)
        - Static route Import (530)
        - Two-Way Route Import (533)
     - Config Policy-Based Route Optimization (535-542 / 05:05:49 - 05:16:36) - продолжение задачи настройки 
     - Config PBR (543-546 / 05:16:36 - 05:18:00)
  - Case Analysis (547-561 / 05:18:00 - 05:26:00)
     - Case I (547-551 / 05:18:00 - 05:23:00)
     - Case II (552-561 / 05:23:00 - 05:26:00)
- LAB GUIDE Л/Р 10 (184-200 / 05:26:00 - 05:34:00) 

___Примечания:___

Лаба 9. Делаем по "обычному" лабгайду. На роутере 6 нет предконфиги - его настраиваем с "нуля". Роутеры запускаем поочередно, иначе может не применяться исходная конфига. Делаем До 12-20 мск Далее начнём перед обедом теорию (Route Control) и после обеда продолжим (ориентировочно до 15-00) Далее доделывание лабы 9 (кто не успеет сделать полностью ) и лаба 10. 

В шаге на стр.156 в лабгайде в команде опечатка 
```
[R4]ip community-filter 10 deny 100:200
```
 нужно

```
[R4]ip community-filter 10 permit 100:200
``` 
Если что - в итоговой конфиге в конце лабы команды представлены правильно.

![](GIT/Mikrotest/HCIE/HCIE%20CAMP%202021/BL_03_L05%20-%2020210621/pictures/01.jpg)

Имеет смысл прослушать перед OSPF (BL01_L02)

ACL - освоить практически, так как фильтрация, необходима на лабе