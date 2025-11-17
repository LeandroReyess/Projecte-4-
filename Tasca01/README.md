# 🛡️ T01 — DRP: Còpies de Seguretat  
## Estudi del Cas Client (Treball Cooperatiu)

## 📌 Breu Descripció
Aquesta tasca forma part del **Projecte 4** i introdueix el **pla de recuperació davant desastres (DRP)** centrat en les **còpies de seguretat**.  
El treball combina fases individuals, en parelles i en grup per analitzar un cas real d’empresa i dissenyar una política de backups funcional i professional.

---

# 🟦 Introducció
Durant la primera hora, el responsable de seguretat de l’empresa presenta els conceptes essencials de les còpies de seguretat a partir d’un material didàctic.  
Posteriorment, els estudiants treballen aquests aspectes mitjançant una dinàmica cooperativa dividida en tres fases.

---

# 🏢 Cas Client: **Muntatges i Serveis Tècnics SL**
Empresa dedicada a la instal·lació i manteniment d’equips industrials.

## 🔧 Infraestructura Tècnica
### 📁 **Servidor de Fitxers (Ubuntu Server)**
- **Documents de Projecte**  
  Plànols, especificacions tècniques  
  *300 GB, creixement moderat*
- **Bases de Dades (Comptabilitat i Clients)**  
  *20 GB, canvi constant, informació crítica*
- **Carpetes Personals**  
  *100 GB, ús diari*

### 🖥️ **10 Equips Clients (Windows 10/11)**
- Ús principal: Treball amb fitxers del servidor  
- Alguns tècnics guarden arxius temporals importants localment

### 🌐 **Connexió a Internet**
- Fibra simètrica **600 Mbps**

---

# ⏱️ Requisits de Recuperació
- **RTO (Temps màxim d’inactivitat):**  
  Dades de Comptabilitat/Clients disponibles en < **4 hores**
- **RPO (Pèrdua de dades admissible):**  
  - La majoria de dades: fins a **24 hores**  
  - Comptabilitat/Clients: màxim **4 hores**
- **Retenció mínima:** **1 mes** d’històric

---

# 🟩 Fase 1 — Treball Individual

Respon individualment, basant-te en el cas:

### **1️⃣ Què copiar? (Priorització)**
- Quines són les dades més crítiques del servidor?
- Cal copiar els 10 equips clients? *Justifica-ho.*

### **2️⃣ Periodicitat i Tipus de Còpia**
Proposa un calendari setmanal:
- Diari / Setmanal / Mensual  
- Tipus de còpia: **Completa / Diferencial / Incremental**

### **3️⃣ Mitjans i Ubicació**
- Tipus de mitjà: **Disc extern, NAS, Cloud, Cintes...**
- Compliment de la regla **3-2-1**  
  (3 còpies, 2 mitjans diferents, 1 fora del lloc)

---

# 🟦 Fase 2 — Treball per Parelles

1. Compareu les respostes individuals.  
2. Dissenyeu un **esquema 3-2-1 unificat**.

### 📋 **Taula per omplir**

| Element | Proposta de la Parella | Justificació |
|--------|-------------------------|--------------|
| **Dades Crítiques** | | |
| **Periodicitat (BD)** | | |
| **Tipus de Còpia (BD)** | | |
| **Mitjà 1 (Local)** | | |
| **Mitjà 2 (Extern)** | | |
| **Ubicació Fora del Lloc** | | |

---

# 🟧 Fase 3 — Treball en Grup

### 1️⃣ Debat i Selecció
Cada parella presenta el seu esquema.  
El grup avalua cada proposta considerant:
- Cost  
- Temps de recuperació  
- Seguretat  
- Simplicitat i manteniment  

### 2️⃣ Política Final de Còpies de Seguretat
El grup redacta el document final que s’entregarà a l’empresa.

---

# 📄 Document Final (a lliurar pel grup)

## **1) Dades Objecte de Còpia**
- Separant **Servidor** / **Clients**
- Dades **crítiques** i **no crítiques**
- Freqüència de còpia per tipus de dada

---

## **2) Cronograma Setmanal Detallat**

| Dia | Dades | Tipus de Còpia | Mitjà |
|-----|-------|----------------|--------|
| Dilluns | | | |
| Dimarts | | | |
| Dimecres | | | |
| Dijous | | | |
| Divendres | | | |
| Dissabte | | | |
| Diumenge | | | |

---

## **3) Mitjans i Ubicació (Regla 3-2-1)**

### 🖥️ **Mitjà 1 (Local):**
*(exemple: NAS intern, disc dur USB empresarial, etc.)*

### ☁️ **Mitjà 2 (Extern):**
- Opcions: Cloud (Azure, AWS, Google Cloud), Cintes LTO, servei extern
- Proveïdor recomanat

### 📦 **Ubicació Fora del Lloc:**
- Ubicació física o lògica
- Responsable del manteniment de la còpia externa

---

## **4) Estratègia de Recuperació (RTO/RPO)**
Explicar com es garanteix:
- **RTO ≤ 4 hores**
- **RPO ≤ 4 hores** per Comptabilitat/Clients  
Mitjançant:
- Tipus de còpia seleccionats  
- Freqüència  
- Velocitat de restauració  
- Organització de dades i mitjans  

---

# 📚 Materials i Enllaços de Suport

- **Moodle 0226 Seguretat Informàtica – RA2.AA3 Còpies**
- **INCIBE — Guia de còpies de seguretat**  
- **Xataka – Mètode Backup 3-2-1** (YouTube):  
  https://youtu.be/PM_M4Iz6I4o?si=F7DRyDDTZE3hjWn8

---

# ✔️ Estat de la Tasca T01
- [x] Estudi del cas  
- [x] Fase individual  
- [x] Fase en parelles  
- [x] Fase en grup  
- [x] Política final redactada *(pendent d’entrega)*  

---

# ✨ Autor
Document elaborat per l’estudiant dins la tasca **T01 – DRP: Còpies de Seguretat** del Projecte 4.


