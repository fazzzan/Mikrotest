___Материал 6-го дня___ 

Доп. материалы
HCIE-R&S+Theory+v1.1.pdf
01_+HCIE-R&S_Huawei_Certified_Internetwork_Expert-Routing_and_switching_material-v1.1.pdf - есть примеры, который отсутствуют в нашем учебнике

- MLD (563-593 / 00:00:00 - 00:45:17)
  - MLD Overview (567-568 / 00:04:09 - 00:13:35) - аналог IGMP, транспорт - ICMPv6
  - MLD v1 (570-YY / 00:14:01 - 00:31:45)
     - Querier Election (571-572 / 00:19:08 - 00:22:29)
     - Group Member Join 572-573 / 00:22:29 - 00:28:00)
     - Group Member Leave (574-574 / 00:28:00 - 00:31:45)
  - MLD v2 (575-YY / 00:31:45 - 00:39:16)
     - MLDv2 Query Mess Format (576 / 00:31:45 - 00:33:33)
     - MLDv2 Report Mess Format (577 / 00:33:33 - 00:36:00)
        - 01_+HCIE-R&S_Huawei_Certified_Internetwork_Expert-Routing_and_switching_material-v1.1.pdf (558-559 / 00:34:32 - 00:35:12)
     - Group-Source-Specific Query (578-579 / 00:36:00 - 00:39:16)
  - MLG Config Example (580-584 / 00:39:16 - 00:41:39)
  - SSM Mapping (585-593 / 00:41:41 - 00:45:17)
     - MLD SSM Mapping (586 / 00:41:41 - 00:44:37)
     - Config MLD SSM Mapping (587-593 / 00:44:37 - 00:45:17)

- PIM (594-650 / 00:45:17 - 01:55:00)
  - PIM-SM [sparse mode] Mechanism Overview (597-600 / 00:45:17 - 01:43:35)
     - Multicast protocols (598-599 / 00:46:57 - 00:53:23)
     - Protocols Used in MC  (600 / 00:53:23 - 00:54:10)
     - PIM-SM Overview  (601 / 00:53:23 - 01:05:22)
        - SPT (602 / 00:55:49 - 00:59:02)
        - RPT (603 / 00:59:15 - 01:03:50)
        - IPv6 PIM-SM Overview (605 / 01:04:00 - 01:05:22)
     - DR Election (606-608 / 01:05:22 - 01:21:59)
     - RP Election (609 / 01:21:59 - 01:26:00)
     - Embedded RP fundam (611-612 / 01:26:02 - 01:30:00)
     - Joining the RPT (613-614 / 01:30:13 - 01:33:00)
     - MC Src registration (615 / 01:33:00 - 01:37:23)
     - Stopping the register process (616 / 01:37:23 - 01:38:23)
     - MC traf FWD process (617 / 01:38:23 - 01:39:11)
     - RPT-to-SPT Switchover (During Switchover) (618 / 01:39:11 - 01:41:17)
     - Pruning after Switchover (619 / 01:41:17 - 01:43:35)
  - IPv6 PIM-SM Config (620-630 / 01:43:35 - 01:55:00)
  

 LAB GUIDE Л/Р 11 (201 - 220 / 01:55:00 - 01:56:30) 

  - IPv6 PIM-SSM Fundam (631-636 / 01:57:00 - 02:01:50)
     - IPv6 PIM-SSM Overview (632 / 01:57:00 - 01:58:30)
     - IPv6 PIM-SSM Fundam (633 / 01:58:30 - 01:59:00)
     - IPv6 PIM-SSM Config Ex (634-636 / 01:59:00 - 02:01:50)
  - Multicast Route Mgm (637-646 / 02:01:50 - 02:23:55)
     - MC Route MGM (638 / 02:01:50 - 02:09:28)
        - IPv6 MC protocol routing table (639 / 02:05:26 - 02:06:39)
        - IPv6 MC routing table (640 / 02:06:39 - 02:08:47)
        - MFIB (641 / 02:08:47 - 02:09:28)
     - RPF Check (642-YY / 02:09:28 - 02:20:15)
        - Доп. 00_HCIE1.1-R&S_Huawei_Certified_Internetwork_Expert-Routing_and_switching_material-v1.1.pdf (713-715 / 02:09:28 - 02:12:45)
     - MC load Splitting (645-YY / 02:20:15 - 02:23:55)
        - Доп. 00_HCIE1.1-R&S_Huawei_Certified_Internetwork_Expert-Routing_and_switching_material-v1.1.pdf (614-616; 725-728 / 02:21:00 - 02:23:45)
        - MC fwd without & with MC Load Splitting (646 / 02:23:45 - 02:23:55) - смотреть под допам, материал с ошибками
  - Typical IPv6 Multicast APP (647-650 / 02:24:00 - 02:24:19)
     - Intra-domain MC (648 / 02:24:00 - 02:24:19)

https://support.huawei.com/enterprise/en/doc/EDOC1000091883/955ce715/what-flags-are-commonly-used-in-a-pim-routing-table

LAB GUIDE Л/Р 12 (221 - 252 / 06:40:45 - 07:19:12)
LAB GUIDE Л/Р 13 (253 - 282 / 06:40:45 - 07:19:12)

- Д/З 3 (Z:\HOMEWORK) MPLS, MPLS_VPN,  (материал в txt / 02:26:00 - 07:01:23)
ДЗ 3-й недели, состояит из 3 заданий (есть видео в конце 6-го дня):
- 1-е задание MPLS, MPLS_VPN - по Lab GUIDE MPLS VPN; MPLS
- 2-е задание (02:36:00 - ) стык из OSPF+IS-IS - предотвратить появление петель маршрутизации
   - 1,2 п.п - уже сконфигурированы
   - 3 - на R6 завести в OSPF  через редистрибуцию. OSPF NE - not Edge, просто OSPF роутер
   - 4 - НаR3, R4: взаимная редистрибуция для префиксов со 172.16
      - cost - метрика должна наследоваться при редистрибуции
      - Lo0 - по оптимальном у пути (10-я лаба)
- 3-е Задание (02:27:21-02:36:00): Часть оборудования преднастроена (ошибочка в п.п. 2 - смотреть в видео)
   - настроить взаимную редистрибуцию ISIS<->BGP подсетей всех IF Loopback
   - сделать матчинг по октету (чет-нечет), то есть добиться разнесения маршрутов (src/dst), чтобы при обращении к lo R5:
      - до нечетных IP - маршрут был через верх
      - до четных IP - маршрут был через низ
   -  избежать dual-node bi-directional route importing - предотвратить петли

Корректная схема
 ![](pictures/01.jpg)



