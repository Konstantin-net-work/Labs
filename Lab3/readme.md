# Домашняя работа №3
## Underlay. IS-IS

**Цель:**  
настроить IS-IS для Underlay сети.

### План работ:

Настроите ISIS в Underlay сети, для IP связанности между всеми сетевыми устройствами.
Зафиксируете в документации - план работы, адресное пространство, схему сети, конфигурацию устройств
Убедитесь в наличии IP связанности между устройствами в ISIS домене

<div align="center">
  <img src="../Lab1/1.webp" alt="Схема CLOS" width="600">
  <br>
  <i>Рис. 1. Топология сети</i>
</div>

<br>

### Таблица адресации

<img src="../Lab1/2.webp" alt="Адресное пространство" width="600">
<br>

| Устройство | Адрес Loopback |
|------------|----------------|
| Spine-1    | 10.1.1.1       |
| Spine-2    | 10.1.1.2       |
| Leaf-1     | 10.1.2.1       |
| Leaf-2     | 10.1.2.2       |
| Leaf-3     | 10.1.2.3       |

### Пример настройки устройств
## Spine-1

```bash
router isis 1
   net 49.0001.0010.0001.0001.0001.00
   router-id ipv4 10.1.1.1
   is-type level-2
   log-adjacency-changes
   !
   address-family ipv4 unicast
```

```bash
interface Ethernet1
   description to-Leaf-1
   no switchport
   ip address 10.0.1.0/31
   isis enable 1
   isis network point-to-point
```
```bash
interface Loopback1
   ip address 10.1.1.1/32
   isis enable 1
```

После настройки интерфейсов была проведена проверка связанности ping'ом .

<img src="Ping+trace/L1-to-L2-3_ping.png" alt="проверка 1" width="600">
<img src="Ping+trace/L1-to-L2-3_ping_tr_offspine_1.png" alt="проверка 2" width="600">


# P.S. Во время настройки была допущена ошибка в "net"
Но по причине того что адресация всех устройств начинается с актета "10" оно не отразилось на работоспособности настроеной схемы
<img src="Area_addr-error/Leaf-1-area-addr.png" alt="проверка 1" width="600">
<img src="Area_addr-error/Leaf-2-area-addr.png" alt="проверка 2" width="600">
