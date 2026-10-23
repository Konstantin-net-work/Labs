# Домашнее задание №2
## Underlay. OSPF

**Цель:**  
Настроить OSPF для Underlay сети.

### План работ:
1. Настроить OSPF в Underlay сети для IP-связности между всеми сетевыми устройствами.
2. Зафиксировать в документации план работы, адресное пространство, схему сети и конфигурацию устройств.
3. Убедиться в наличии IP-связности между устройствами в OSPF-домене.


### Конфигурация устройств

#### Пример настройки OSPF-процесса (Spine-1)

```bash
router ospf 1
   router-id 10.1.1.1
   max-lsa 12000
```

#### Настройка Loopback-интерфейса

```bash
interface Loopback1
   ip address 10.1.1.1/32
   ip ospf area 0.0.0.0
```

#### Настройка физического интерфейса (пример для Leaf-3)

```bash
interface Ethernet2
   description to-Spine-2
   no switchport
   ip address 10.0.2.5/31
   ip ospf network point-to-point
   ip ospf area 0.0.0.0
```

Скриншоты проверок:
<div align="center">
  <img src="8.webm" alt="Проверка 1" width="600">
  <br>
  <i>Рис. 1.</i>
</div>
<div align="center">
  <img src="9.webm" alt="Проверка 1" width="600">
  <br>
  <i>Рис. 1.</i>
</div>
