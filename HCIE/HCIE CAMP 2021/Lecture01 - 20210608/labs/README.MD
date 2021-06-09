20210608

![](pictures/01.jpg)

Задача:
сконфигурировать MSTP, и разнести по разным рутам разные VLAN

```
system-view 
sysname SwitchA 
 
### Добавляем VLAN
vlan batch 2 to 20

### Конфигурим Eth-trunk 1 из двух IF
interface Eth-Trunk 1 
trunkport gigabitethernet 0/0/2 
trunkport gigabitethernet 0/0/3 
port link-type trunk 
port trunk allow-pass vlan 2 to 20
quit

### Транк на аплинке
interface gigabitethernet 0/0/1
port link-type trunk 
port trunk allow-pass vlan 2 to 20 
quit 

### Конфигурируем MST регион
stp region-configuration
region-name RG1 
instance 1 vlan 2 to 10 
instance 2 vlan 11 to 20 
active region-configuration 
quit 

### Задаем ROOT для соответствующего MSTI (на втором свиче - наоборот)
stp instance 1 root primary
stp instance 2 root secondary

```

Видно как уже работает MSTP для разных MSTI: рутом делается сосед

![](pictures/03.jpg)

```

### Включение проприетарщины HUA для расчета pathcost
stp pathcost-standard legacy

### Включение Security на DP у рута вниз, к ACCESS-SW
interface gigabitethernet 0/0/1
stp root-protection
quit

### Включаем STP
stp enable
```
проверка:
Видно работу за регион
```displa stp region-configuration```
![](pictures/04.jpg)

```display stp instance 2 | include Root```
![](pictures/05.jpg)

```display stp topology-change```
![](pictures/06.jpg)


Итак MSTP построено таким образом:
- регион 1
- MSTI1 - primary SwitchA
- MSTI2 - primary SwitchB
- Транковые порты ACCESS-уровня Gi0/0/2 - имеют высокую стоимость и будут в состоянии ___ALTE  DISCARDING___:
   - Слева для MSTI2 (stp instance 2 cost 20000)
   - Справа для MSTI1 (stp instance 1 cost 20000)
- Так как правильно настроена стоимость, использоваться до Distribution уровня будут аплинки, а для достижения нужного рута - Eth-trunk. Выглядеть это будет как нарисовано на схеме стрелочками:  
   - если трафик VLAN 2-10 (MSTI1) окажется на SwitchD, то он пойдет через верх налево 
   - если трафик VLAN 11-20 (MSTI2) окажется на SwitchC, то он пойдет через верх направо

![](pictures/07.jpg)

- Только в случае отвала аплинка, MSTP перестроится и трафик пойдет через промежуточный транк между ACCESS свичами  

![](pictures/08.jpg)