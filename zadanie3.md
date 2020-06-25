# Zadanie 3 sk2020

# Adresy i sieci

W zadaniu użyto sieci 160.160.100.0/22. Wykorzystano podsieć rozmiaru /22 pozwalającej zaadresować co najmniej 600 urządzeń w sieci. 

# Oprogramowanie wykorzystane do realizacji poszczególnych wymagań

- Wirtualizacja systemu Linux: Virtualbox 
- Dystrybucja Linux: Linux Alpine 
- NAT: iptables 
- DHCP: dhcpd
- DNS: dnsmasq

# Kluczowa konfiguracja oprogramowania pozwalająca na odtworzenie stanu po reinstalacji środowiska
- net.ipv4.ip_forward = 1

iptables: 
- Chain POSTROUTING (policy ACCEPT) MASQUERADE all -- anywhere anywhere

DHCP: 
-   subnet 168.150.100.0 netmask 255.255.252.0
	{
    
    range 168.150.100.1 168.150.103.254;  
    option routers 168.150.100.1;  
    option domain-name-server 168.150.100.1, 1.1.1.1
    
    }

DNS hosts: 

-  168.150.101.50 erp.mojaorganizacja.pl,
-  168.150.102.50 router.mojaorganizacja.pl
-  168.150.103.50 drukarka.mojaorganizacja.pl

host printer {hardware ethernet 168.150.101.30;}

Interfejsy sieciowe:

-   serwer DHCP:  
    auto eth0  
    iface eth0 inet dhcp  
    
    auto eth1  
    iface eth1 inet static  
    address 168.150.100.1  
    netmask: 255.255.252.0
    
-   drukarka podpięta wpięta sieci:
    
    auto eth0  
    iface eth0 inet static  
    address 168.150.100.6  
    netmask: 255.255.252.0  
    
-   pozostałe urządzenia w sieci:  
    auto eth0  
    iface eth0 inet dhcp
