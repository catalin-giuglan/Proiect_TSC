# Proiect TSC

### Schema bloc și fișierul BOM

![image](https://github.com/user-attachments/assets/f632e464-27ee-4a00-a967-a242c95c3ac1)

[Google Drive Link]([https://drive.google.com/drive/u/0/folders/1svHynGlwr7JKA02n5Jt7F-PYmH98pda1](https://docs.google.com/spreadsheets/d/16zDlMAK-QEJo3e8-mDt3CT91WrjNDixEgXfPSYE8hOI/edit?usp=drive_link))

### Componentele au fost procurate de pe:
- [Mouser](https://eu.mouser.com/)
- [Comet](https://www.comet.srl.ro/)

### Examinare 3D a dispozitivului:
- Pentru a vedea în Fusion ce este în spatele ecranului:
  - Apasă Hide pe Browser -> Bodies -> Box: vei vedea placa și bateria.

- Sketch 43 reprezintă bateria.
- Sketch 44 reprezintă ecranul.
- Pentru a vedea imagini cu dispozitivul, caută în directorul Images al acestui repository.

---

### Descriere Proiect:

## Ebook Reader - Proiect realizat în Autodesk Fusion

Acest proiect reprezintă dezvoltarea unui ebook reader, realizat cu ajutorul software-ului Autodesk Fusion și al librăriei Desk Assistant. În cele ce urmează sunt descriși pașii principali ai realizării proiectului, de la montarea schematicului, până la integrarea 3D finală și pregătirea fișierelor necesare.

# 1. Instalarea librăriei Desk Assistant

Proiectul a debutat cu instalarea librăriei Desk Assistant, care a oferit acces la toate componentele necesare: rezistențe, condensatori, butoane și altele. Această librărie a constituit baza proiectării și implementării electronice.

# 2. Realizarea schematicului

Am început prin crearea schematicului — un fișier 2D în care am conectat componentele între ele conform cerințelor. Schematicul a fost realizat cu precizie, respectând topologia și conexiunile specificate.

# 3. Implementarea PCB-ului

După finalizarea schematicului, am trecut la partea de PCB layout. Am poziționat toate componentele conform dimensiunilor și constrângerilor date în enunț. Am realizat rutarea circuitelor și am corectat erorile apărute în timpul procesului.

# Am ținut cont de:

-- Fișierul DRC (Design Rule Check) – pentru validarea regulilor de proiectare
-- Constrângerile privind grosimea cablurilor – pentru asigurarea unei funcționări optime

# 4. Modelare 3D

Pentru realizarea modelului 3D:
-- Am descărcat și poziționat modelele 3D ale fiecărei componente în parte
-- Le-am mapat la corespondentele lor 2D
-- Am actualizat schema 3D în urma fiecărei mapări
-- La final, am integrat întreaga placă în carcasa oferită în enunț, alături de o baterie și un display

# 5. Fișiere auxiliare

Pentru finalizarea cerințelor, am generat:
Fișierul BOM (Bill of Materials)
Fișierul CAM necesar pentru fabricarea PCB-ului

# 6. Prezentare și livrare

Am realizat capturi de ecran relevante pentru a evidenția modul în care arată placa 3D și modul de integrare în carcasă. Proiectul complet a fost încărcat pe GitHub, împreună cu acest fișier README.md care documentează procesul de realizare.

---

### Componente Hardware folosite:
- **ESP32-C6**: Microcontroller principal, care asigură conectivitatea și procesarea datelor.
- **E-Paper Display**: Display cu consum redus de energie, conectat prin interfața SPI.
- **Senzor de Mediu BME688**: Măsoară parametrii de mediu și trimite date prin interfața I2C.
- **Memorie NOR Flash 64MB**: Stocare extensibilă pentru fișiere de e-book.
- **Modul RTC DS3231SN**: Oferă funcționalitate de ceas în timp real.
- **Conector USB-C**: Încărcare și transfer de date.
- **Baterie Li-Po**: Alimentare principală a dispozitivului.
- **Conectori pentru SD Card**: Pentru extinderea memoriei și stocarea cărților.

---

### ESP32-C6:
- **GPIO pinii** sunt utilizați pentru conectarea senzorilor și a altor componente periferice.
- **SPI** pentru E-Paper și memorie Flash.
- **I2C** pentru senzorul de mediu.

**Interfețe principale:**
- **SPI**: Conectează ecranul E-Paper și memoria Flash.
- **I2C**: Conectează senzorul BME688 și modulul RTC.
- **UART**: Pentru comunicație serială.

**Pini Utilizați - ESP32-C6:**
- **GPIO16**: TX pentru comunicație serială.
- **GPIO17**: RX pentru comunicație serială.
- **GPIO21**: SDA pentru I2C.
- **GPIO22**: SCL pentru I2C.
- **GPIO18, GPIO19**: SCK și MISO pentru SPI.
- **GPIO5**: Chip Select pentru memorie Flash.
- **GPIO4**: Reset pentru E-Paper.

---

### Probleme și gestionarea erorilor:
- A fost necesara aprobarea a 2 erori de tip "smd-hole", deoarece o piesa era defecta.

- Pentru TP-uri nu am gasit un model 3D online, asa ca a fost nevoie sa folosesc un cilindru cu partea de sus putin rotunjita.

- Am folosit un numar de vias-uri cam mare pentru a evita erorile de overlap.

---
