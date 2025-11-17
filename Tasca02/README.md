# 🛡️ T02 — DRP: Còpies de Seguretat  
## Cas Pràctic: Implementació i Prova de la Política de Backups

## 📌 Breu Descripció
Aquesta tasca posa en pràctica la política de còpies de seguretat dissenyada a la T01.  
L’objectiu és crear **guies tècniques amb proves reals** perquè el personal de "Muntatges i Serveis Tècnics SL" pugui aplicar el seu pla de recuperació davant desastres amb autonomia i seguretat.

El treball es divideix en dues parts:
1. **Còpies de seguretat en un equip Windows (Duplicati)**
2. **Còpies de seguretat en un servidor Linux (Duplicity + cron)**

---

# 🟦 Introducció al Cas
En la tasca anterior s’ha definit una política de còpies per al client. Ara és necessari convertir aquella teoria en una **prova de concepte** documentada: instal·lacions, configuracions, captures, restauracions i scripts.

Aquest document servirà com a guia operativa per al personal de l’empresa.

---

# 🟩 PART 1 — Còpia de Seguretat en Windows (Duplicati)

Tot i que el DPR original no incloïa còpies als equips clients, el director de l’empresa guarda informació important al seu PC i demana una excepció.

## 🎯 Objectiu
Implementar un esquema **3-2-1**:
- **Còpia local** → disc secundari del PC  
- **Còpia externa** → Google Drive via Duplicati  
- **3 còpies, 2 mitjans diferents, 1 fora del lloc**

## 🖥️ Prova de Concepte (Windows 11)
Heu de crear:
- Una màquina virtual **Windows 11**
- Dos discos:
  - **Disc 1** → sistema operatiu
  - **Disc 2 (10 GB)** → emmagatzematge de backups

Per a Google Drive, cal utilitzar un **compte no escolar**.

## ⏱️ Política de còpies
- **Cada hora** → còpia de seguretat del perfil d’usuari al disc secundari  
- **18:00** → còpia completa o incremental a Google Drive

---

## 📝 Procediment a documentar

### **1️⃣ Instal·lació de Duplicati**
Incloure:
- Descàrrega
- Instal·lació
- Primer inici i configuració bàsica

### **2️⃣ Creació del Pla de Còpia Local (disc secundari)**
- Selecció de carpetes (Documents, Escriptori, AppData si cal)
- Escaneig inicial
- Configuració d’horaris (cada hora)
- Validació del volum de dades

### **3️⃣ Configuració del Pla de Còpia al Cloud**
- Connexió amb Google Drive
- Gestió del token d’autenticació
- Política d’encriptació
- Programació a les 18:00

### **4️⃣ Simulació i proves**
- Crear fitxers a *Documents*
- Observar com Duplicati els afegeix a la còpia programada
- Revisar versions i registres

### **5️⃣ Restauració des del disc secundari**
- Esborrar el contingut de *Documents*
- Executar restauració
- Verificar que es recuperen totes les dades i la seva integritat

### **6️⃣ Restauració des del Cloud**
- Simular una pèrdua total de dades
- Provar restauració des de Google Drive
- Validar funcionament i temps aproximat

---

# 🟧 PART 2 — Còpia de Seguretat en Servidor Linux  
## Herramienta: **Duplicity**

Duplicity permet fer còpies en local o remot i incorpora xifratge automàtic.  
Combinat amb **cron**, permet implementar polítiques avançades de backup.

---

# 🖥️ Prova de Concepte (Ubuntu Server)

Cal crear una màquina virtual amb:
- **Ubuntu Server**
- **Disc secundari de 10 GB** (simularà unitat externa)

## 📝 Procediment detallat

### **1️⃣ Preparació de la unitat de backup**
- Inicialitzar disc
- Formatar en **XFS**
- Crear directori `/media/backup`
- Muntar manualment la unitat

### **2️⃣ Instal·lació de Duplicity**
Comandes necessàries i verificació de versió.

### **3️⃣ Creació d’usuaris i dades de prova**
- Crear 2 usuaris nous  
- Crear 4 fitxers de 10 MB a `home/usuari`  
  (poden generar-se amb `dd` o `fallocate`)

### **4️⃣ Primera còpia completa**
- Fer backup de `/home`
- Comprovar estructura, xifrat i resultat

### **5️⃣ Restauració**
- Esborrar fitxers de prova
- Restaurar-los amb Duplicity
- Validar que recuperen mida i contingut

### **6️⃣ Crear canvis i executar còpia incremental**
- Afegir fitxer de 4 MB
- Crear nova còpia
- Verificar logs → Duplicity detecta canvis incrementals

---

# 🔄 Automatització amb Scripts i Cron

## 🔐 Requisit de seguretat
La unitat de backup ha d’estar **desmuntada per defecte**.  
Només s’ha de muntar mentre s’executa la còpia.

---

## 📝 Scripts necessaris (amb permisos +x)

### **7️⃣ Script: `fullbackup.sh`**
Ha de:
- Muntar la unitat
- Exportar variable d'entorn:  
  `export PASSPHRASE=contrasenya`
- Fer còpia completa de `/home`
- Desmuntar la unitat

### **Programació al cron**
- Execució com a root  
- **Diumenges a les 23:00**

---

### **8️⃣ Script: `incrementalbackup.sh`**
Ha de:
- Muntar unitat
- Exportar `PASSPHRASE`
- Fer còpia incremental
- Desmuntar unitat

### **Programació al cron**
- Execució com a root  
- **Dilluns → Dissabte a les 23:00**

---

# 📚 Materials i Enllaços de Suport

- 🔗 Duplicati — https://duplicati.com/  
- 🔗 Creació d’arxius amb *fsutil* (Windows):  
  https://waytoit.wordpress.com/2015/03/15/creando-archivos-con-fsutil/
- 🔗 Creació d’arxius de prova en Linux:  
  https://waytoit.wordpress.com/2015/03/21/creando-archivos-de-prueba-en-linux/
- 🔗 Duplicity — pàgina oficial:  
  http://manpages.ubuntu.com/manpages/trusty/man1/duplicity.1.html
- 🔗 Programar tasques amb cron:  
  https://geekytheory.com/programar-tareas-en-linux-usando-crontab

---

# ✔️ Estat de la Tasca T02
- [x] Part 1 – Prova de concepte en Windows  
- [x] Part 2 – Prova de concepte en Linux  
- [x] Scripts creats  
- [x] Cron configurat  
- [ ] Documentació completa amb captures *(pendent d’afegir)*

---

# ✨ Autor
Document elaborat per l’estudiant dins la tasca **T02 – DRP: Còpies de Seguretat. Cas Pràctic** del Projecte 4.


