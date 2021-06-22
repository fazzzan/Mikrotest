Лаба 9. Делаем по "обычному" лабгайду. На роутере 6 нет предконфиги - его настраиваем с "нуля". Роутеры запускаем поочередно, иначе может не применяться исходная конфига. Делаем До 12-20 мск Далее начнём перед обедом теорию (Route Control) и после обеда продолжим (ориентировочно до 15-00) Далее доделывание лабы 9 (кто не успеет сделать полностью ) и лаба 10. В шаге на стр.156 в лабгайде в команде опечатка [R4]ip community-filter 10 deny 100:200 нужно [R4]ip community-filter 10 permit 100:200 —--------------— 
Если что - в итоговой конфиге в конце лабы команды представлены правильно.

Доп. материалы
12 Traffic Filtering and Forwarding Path Control.pdf
11 Routing Policy and Route Control.pdf

___Материал 5-го дня___ 
- Route Import and Control  (487-561 / 0X:XX:00 - 0X:XX:00)
  - Route Filter (491-509 / 0X:XX:00 - 0X:XX:00)
     - ACL (491-498 / 0X:XX:00 - 0X:XX:00)
     - IP Prefix List (499-504 / 0X:XX:00 - 0X:XX:00)
     - AS-Path Filter (505-507 / 0X:XX:00 - 0X:XX:00)
     - Community Filter (508-509 / 0X:XX:00 - 0X:XX:00)
  - Routing policy and PBR (510-525 / 0X:XX:00 - 0X:XX:00)
     - Routing policy (511-518 / 0X:XX:00 - 0X:XX:00)
     - PBR (519-523 / 0X:XX:00 - 0X:XX:00)
     - Comparision Routing Policy & PBR (524-525 / 0X:XX:00 - 0X:XX:00)
  - Routing policy and PBR Config ommand (526-546 / 0X:XX:00 - 0X:XX:00)
     - Config route Import (527-534 / 0X:XX:00 - 0X:XX:00)
     - Config Policy-Based Route Optimization (535-542 / 0X:XX:00 - 0X:XX:00)
     - Config PBR (543-546 / 0X:XX:00 - 0X:XX:00)
  - Case Analysis (547-561 / 0X:XX:00 - 0X:XX:00)
     - Case I (547-551 / 0X:XX:00 - 0X:XX:00)
     - Case II (552-561 / 0X:XX:00 - 0X:XX:00)

- LAB GUIDE Л/Р XX (XX-XX / 06:40:45 - 07:19:12) 

Роут-фильтеринг - работает с базовыми ACL

negative match - концепт HUA, пакет не попал в явный deny.

ACL - лучше именованные



___Материал XX-го дня___ 
- I (XX-YY / 0X:XX:00 - 0X:XX:00)
  - II (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
  - II (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
  - II (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
- I
  - II (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
  - II (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
  - II (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
- I
  - II (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
  - II (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
  - II (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)
     - III (XX-YY / 0X:XX:00 - 0X:XX:00)