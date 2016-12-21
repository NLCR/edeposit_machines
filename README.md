# E-deposit stroje
Infrastruktura pro stroje E-depositu

## Vagrant - Testovací prostředí s Centos/7 a LXC
závislost:  ansible 2.2.0.0

vagrant up nahodí box 'centos/7' a ansible do něj nainstaluje základní konfiguraci stroje + LXC prostředí
```
git clone https://github.com/NLCR/edeposit_machines.git
cd edeposit_machines
vagrant up
```

## Popis řešení

### Portálový server
Portálový server je určený pro přístup z internetu - přístup producentů. Portálový server je viditelný z internetu na portu 443. Pro https přístup doporučujeme zakoupit OV HTTPS certifikát. Portálový server se připojuje na aplikační server. Portálový server se připojuje na Aleph X services pro čtení metadat.

### Aplikační server
Aplikační server obsahuje software SAFE a slouží k přístupu pracovníků NK. Server je viditelný pro pracovníky NK na portu 80 a 443. Aplikační server je viditelný pro komponentu zajišťující export do Alephu na portu 22 (SSH). Aplikační server má přístup na SMTP pro rozesílání informačních emailů v rámci NK a pro producenty obsahu. Aplikační server se připojuje na databázový server. Aplikační server má přístup do importního adresáře SAFE LTP. Aplikační server se připojuje na Aleph X services pro čtení metadat.

### Databázový server
Databázový server slouží k uložení metadat a elektronických souborů.
