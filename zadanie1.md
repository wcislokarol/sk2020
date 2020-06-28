# Zadanie 1. na zaliczenie z SK2020

## Adresy w sieci: 
- LAN1 192.158.100.0/22, usable IPs: 192.158.100.1 - 192.158.103.254 (capacity 1022)
- LAN2 192.168.100.0/22, usable IPs: 192.168.100.1 - 192.168.103.254 (capacity 1022)
- LAN3 192.178.100.0/22, usable IPs: 192.178.100.1 - 192.178.103.254 (capacity 1022)

## Tablica rountingu: 
- Router 0: 192.168.100.0/22 via 192.148.0.2 
- Router 0: 192.178.100.0/22 via 192.158.0.3 
- Router 1: 192.158.100.0/22 via 192.148.0.1 
- Router 1: 192.178.100.0/22 via 192.148.0.3 
- Router 2: 192.158.100.0/22 via 192.148.0.2 
- Router 2: 192.168.100.0/22 via 192.158.0.2
