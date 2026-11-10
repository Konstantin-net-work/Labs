# Домашняя работа №3
## Underlay. IS-IS

**Цель:**  
настроить IS-IS для Underlay сети.

### План работ:

Настроите ISIS в Underlay сети, для IP связанности между всеми сетевыми устройствами.
Зафиксируете в документации - план работы, адресное пространство, схему сети, конфигурацию устройств
Убедитесь в наличии IP связанности между устройствами в ISIS домене

<div align="center">
  <img src="//Lab1/1.webp" alt="Схема CLOS" width="600">
  <br>
  <i>Рис. 1. Топология сети</i>
</div>

<br>

### Таблица адресации

<img src="2.webp" alt="Адресное пространство" width="600">
<br>

### Пример настройки интерфейсов 
Spine-1
```bash
!
interface Ethernet1
   description to-Leaf-1
   no switchport
   ip address 10.0.1.0/31
!
interface Ethernet2
   description to-Leaf-2
   no switchport
   ip address 10.0.1.2/31
!
interface Ethernet3
   description to-Leaf-3
   no switchport
   ip address 10.0.1.4/31
!
```
Leaf-1
```bash
!
interface Ethernet1
   description to-Spine-1
   no switchport
   ip address 10.0.1.1/31
!
interface Ethernet2
   description to-Spine-2
   no switchport
   ip address 10.0.2.1/31
```

После настройки интерфейсов была проведена проверка связанности ping'ом .

<img src="3.webp" alt="проверка 1" width="600">
<img src="4.webp" alt="проверка 2" width="600">
