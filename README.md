# CIDR
Exemples et tableaux nbr d'hôte 
**Quelques exemples concrets** pour mieux comprendre **le CIDR (/X)** et son impact sur les adresses IP et les sous-réseaux.

---

## **Exemple 1 : Réseau en /24**
📌 **IP :** `192.168.1.0/24`  
📌 **Masque :** `255.255.255.0`  
📌 **Nombre d'hôtes :** \(2^8 - 2 = 254\)  
📌 **Plage d'adresses :** `192.168.1.1` → `192.168.1.254`  
📌 **Adresse de broadcast :** `192.168.1.255`  

👉 Ce réseau peut contenir **254 appareils**.

---

## **Exemple 2 : Réseau en /26 (Découpe d'un /24 en 4 sous-réseaux)**
📌 **IP :** `192.168.1.0/26`  
📌 **Masque :** `255.255.255.192`  
📌 **Nombre d'hôtes :** \(2^6 - 2 = 62\)  
📌 **Plage d'adresses :** `192.168.1.1` → `192.168.1.62`  
📌 **Adresse de broadcast :** `192.168.1.63`  

💡 **Si on divise un /24 en 4 sous-réseaux de /26**, voici ce qu’on obtient :

| **Sous-réseau** | **Adresse réseau** | **Plage d'hôtes** | **Broadcast** |
|---------------|----------------|------------------|------------|
| 1 | `192.168.1.0/26` | `192.168.1.1 - 192.168.1.62` | `192.168.1.63` |
| 2 | `192.168.1.64/26` | `192.168.1.65 - 192.168.1.126` | `192.168.1.127` |
| 3 | `192.168.1.128/26` | `192.168.1.129 - 192.168.1.190` | `192.168.1.191` |
| 4 | `192.168.1.192/26` | `192.168.1.193 - 192.168.1.254` | `192.168.1.255` |

👉 **Chaque sous-réseau a 62 hôtes utilisables.**

---

## **Exemple 3 : Réseau en /30 (Pour liaison point-à-point)**
📌 **IP :** `192.168.1.0/30`  
📌 **Masque :** `255.255.255.252`  
📌 **Nombre d'hôtes :** \(2^2 - 2 = 2\)  
📌 **Plage d'adresses :** `192.168.1.1` → `192.168.1.2`  
📌 **Adresse de broadcast :** `192.168.1.3`  

💡 **Les réseaux en /30 sont souvent utilisés pour les connexions entre routeurs**, car ils permettent seulement **2 appareils**.

---

## **Exemple 4 : Grand réseau en /16**
📌 **IP :** `10.0.0.0/16`  
📌 **Masque :** `255.255.0.0`  
📌 **Nombre d'hôtes :** \(2^{16} - 2 = 65 534\)  
📌 **Plage d'adresses :** `10.0.0.1` → `10.0.255.254`  
📌 **Adresse de broadcast :** `10.0.255.255`  

👉 **Ce type de réseau est utilisé pour les grandes entreprises**, car il peut contenir **plus de 65 000 appareils**.

---

## **Résumé : CIDR et nombre d'hôtes**
| **Notation CIDR** | **Masque** | **Nombre d'hôtes** |
|-------------|-----------------|----------------|
| `/30`  | `255.255.255.252` | 2 hôtes |
| `/29`  | `255.255.255.248` | 6 hôtes |
| `/28`  | `255.255.255.240` | 14 hôtes |
| `/27`  | `255.255.255.224` | 30 hôtes |
| `/26`  | `255.255.255.192` | 62 hôtes |
| `/25`  | `255.255.255.128` | 126 hôtes |
| `/24`  | `255.255.255.0`   | 254 hôtes |
| `/23`  | `255.255.254.0`   | 510 hôtes |
| `/22`  | `255.255.252.0`   | 1 022 hôtes |
| `/21`  | `255.255.248.0`   | 2 046 hôtes |
| `/20`  | `255.255.240.0`   | 4 094 hôtes |
| `/19`  | `255.255.224.0`   | 8 190 hôtes |
| `/18`  | `255.255.192.0`   | 16 382 hôtes |
| `/17`  | `255.255.128.0`   | 32 766 hôtes |
| `/16`  | `255.255.0.0`     | 65 534 hôtes |

---

## **Conclusion**
🔹 **Le CIDR indique combien de bits sont réservés pour le réseau.**  
🔹 **Plus le masque est grand (/X augmente), plus on a de sous-réseaux, mais moins on a d’hôtes.**  
🔹 **Chaque masque permet de découper un réseau en plusieurs sous-réseaux de tailles différentes.**  
