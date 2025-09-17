# Networking Lab – Static IP, Ping & DNS

## 🛡️ Στόχος

Δημιουργία ενός μικρού εργαστηριακού περιβάλλοντος με **Windows 11 + Linux Mint**, όπου θα γίνει:

* Στατική IP ρύθμιση σε Linux και Windows
* Αμφίδρομη επικοινωνία μέσω **ping (ICMP)**
* Έλεγχος DNS resolution μέσω **nslookup**

Σκοπός: πρακτική εξάσκηση σε **basic networking, troubleshooting και IT support skills**.

---

## 🖥️ Περιβάλλον

* OS: Linux Mint + Windows 11
* Hardware: 2 Personal PC's 
* Network: Ethernet, ιδιωτικό subnet 192.168.10.0/24

---

## 🔧 Βασικές Ρυθμίσεις & Commands

### Linux Mint

```bash
# Δίνεις στατική IP
sudo ip addr add 192.168.10.10/24 dev enp4s0

# Default gateway
sudo ip route add default via 192.168.10.1

# Έλεγχος
ip addr show
ip route

# Ping προς Windows
ping -c 4 192.168.10.20

# DNS test
sudo apt install dnsutils -y(αν δεν ειναι εγκατεστημένο ήδη)
nslookup google.com
nslookup openai.com
nslookup wikipedia.org
```

### Windows 11 (CMD as admin)

```cmd
netsh interface ip set address "Ethernet" static 192.168.10.20 255.255.255.0 192.168.10.1
ipconfig /all
ping 192.168.10.10
nslookup google.com
nslookup openai.com
nslookup wikipedia.org
```

---

## 🧪 Αποτελέσματα / Screenshots

* ![Linux – ip addr](./screenshots/ip-addr-show-linux.jpg.)
* [Linux – ip route](./screenshots/ip-route.png)
* [Windows – ipconfig](./screenshots/ipconfig.png)
* [Ping Linux → Windows](./screenshots/ping-linux.png)
* [Ping Windows → Linux](./screenshots/ping-windows.png)
* [Linux nslookup](./screenshots/nslookup-linux.png)
* [Windows nslookup](./screenshots/nslookup-windows.png)

**Σημείωση:** Το Linux firewall αρχικά ήταν set σε `deny incoming`, γι’ αυτό η επικοινωνία ICMP απέτυχε μέχρι να προστεθεί το rule για ICMP.

---

## 🧠 Τι Έμαθα

* Ρύθμιση static IP και default gateway σε Linux & Windows
* Αμφίδρομη επικοινωνία δικτύου (ping)
* DNS resolution έλεγχος μέσω nslookup
* Troubleshooting firewall & network configuration

---

## 🛠️ Tools

| Εργαλείο | Χρήση                                           
|Linux Mint|IP routing configuration, DNS testing|
|Windows 11|Static IP configuration, ping, nslookup|
|ping /ICMP|Connectivity testing|
|nslookup  |DNS resolution testing|

---

## 📁 Χρήσιμα Αρχεία (στο repo)

* `report.docx` (πλήρες lab report)
* `screenshots/` (όλα τα captures από Linux & Windows)

---

## 👤 About me

📍 Τεχνικός Υπολογιστικών Συστημάτων, ειδίκευση σε **Networking, Linux, IT Support**
📫 LinkedIn / Email: [kanakismanolis04@gmail.com](mailto:kanakismanolis04@gmail.com)
