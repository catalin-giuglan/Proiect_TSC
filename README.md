# Proiect TSC

### Schema bloc și fișierul BOM

![image](https://github.com/user-attachments/assets/f632e464-27ee-4a00-a967-a242c95c3ac1)

[Tabel BOM](https://docs.google.com/spreadsheets/d/16zDlMAK-QEJo3e8-mDt3CT91WrjNDixEgXfPSYE8hOI/edit?usp=sharing)

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

Pentru a îmbunătăți aspectul descrierii proiectului în README, se pot aplica următoarele modificări pentru a face structura mai clară și prezentarea mai atractivă:

---

# **Descriere Proiect**  

Acest proiect constă în dezvoltarea unui ebook reader, utilizând **Autodesk Fusion** pentru modelare 3D și **librăria Desk Assistant** pentru proiectarea electronică. În cele ce urmează sunt prezentate etapele principale ale realizării proiectului, de la montarea schematicului, până la integrarea finală și generarea fișierelor necesare.

---

## **1. Instalarea librăriei Desk Assistant**  
Proiectul a început prin instalarea librăriei **Desk Assistant**, care oferă acces la componentele esențiale: rezistențe, condensatori, butoane etc. Această librărie a constituit baza pentru proiectarea și implementarea electronică.

---

## **2. Crearea schematicului**  
Am realizat schematicul în format 2D, conectând cu precizie toate componentele conform cerințelor proiectului. Procesul a inclus:  
- **Respectarea topologiilor și conexiunilor** specificate.  
- Crearea unui design clar pentru implementarea ulterioară a PCB-ului.

---

## **3. Implementarea PCB-ului**  
După finalizarea schematicului, am trecut la proiectarea plăcii PCB (layout-ul):  
- **Poziționarea componentelor** conform dimensiunilor și constrângerilor.  
- **Rutarea circuitelor** pentru conexiuni optime.  
- Validarea designului prin **fișierul DRC** (Design Rule Check), respectând toate constrângerile, cum ar fi grosimea cablurilor pentru fiabilitate.

---

## **4. Modelarea 3D**  
Am creat modelul 3D al proiectului utilizând Autodesk Fusion:  
1. Descărcarea și poziționarea **modelelor 3D** ale componentelor.  
2. Maparea acestora cu corespondențele lor din schematicul 2D.  
3. Integrarea plăcii PCB, bateriei și a display-ului în **carcasa proiectată**.

---

## **5. Generarea fișierelor auxiliare**  
Pentru livrarea proiectului, am generat:  
- **Fișierul BOM** (Bill of Materials), care include lista componentelor utilizate.  
- **Fișierul CAM**, necesar pentru fabricarea plăcii PCB.

## **6. Rezolvarea Issue-urilor semnalate**
Pentru a finaliza a doua etapa a proiectului am:
- Citit cu atentie fiecare issue
- Rezolvat problemele semnalate
- Incarcat din nou fisierele de schematic si PCB
- Incarcat imagini noi care sa demonstreze actualizarea proiectului

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
