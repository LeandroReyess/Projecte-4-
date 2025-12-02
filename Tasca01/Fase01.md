### Fase 1

# 1. Què copiar? (Priorització)

Les dades més crítiques del servidor són:

- **La base de dades de Comptabilitat i Clients**, perquè s’utilitza cada dia i qualsevol pèrdua afecta directament l’empresa.
- **Els documents dels projectes** (plànols i documentació tècnica), ja que són el resultat del treball dels tècnics i tenen molt valor.
- **Les carpetes personals dels usuaris**, que també contenen feina important.

Pel que fa a fer còpia dels **10 equips clients**:
- Només cal copiar **les carpetes on els tècnics guarden informes temporals**, ja que la major part de la feina ja està al servidor.
- No val la pena copiar tot l’equip, però sí aquesta carpeta per evitar perdre informes importants.

---

# 2. Periodicitat i Tipus de Còpia

## Cada dia
- **Còpia incremental** de les dades crítiques (bases de dades i documents).
- Per mantenir un **RPO de 4 hores** en la base de dades de Comptabilitat/Clients, fer còpies incrementals cada **4 hores**.

## Cada setmana (diumenge)
- **Còpia diferencial o completa** del servidor sencer.

## Cada mes
- **Còpia completa** i guardada **fora de l’empresa** com a còpia d’històric.

Aquest calendari assegura còpies recents sense saturar l’espai.

---

# 3. Mitjans i Ubicació (Regla 3-2-1)

## Mitjans
- **NAS** per tenir una còpia ràpida i accessible a l’empresa.
- **Còpia al núvol** per garantir una còpia fora del local i protegida davant robatoris, incendis, etc.

## Regla 3-2-1
- **3 còpies** de les dades (la real + 2 còpies).
- **2 tipus de mitjans** diferents (NAS i núvol).
- **1 còpia fora de l’empresa**, que seria la del núvol.

La còpia més recent hauria d’estar al NAS per permetre recuperacions ràpides, mentre que la del núvol serveix com a reserva en casos d’emergència.

### Fase 2

| Element                   | Proposta de la Parella                                | Justificació                                                                                         |
|---------------------------|--------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| **Dades Crítiques**       | Base de dades principal, documents del projecte i informes | Elements essencials per al funcionament i la traçabilitat del cas.                                     |
| **Periodicitat (BD)**     | Còpia diària a final de jornada                        | Evita pèrdues recents i garanteix tenir sempre una versió actualitzada.                                |
| **Tipus de Còpia (BD)**   | Còpia incremental diària + completa setmanal           | Les incrementals estalvien espai i temps; la completa garanteix un punt de restauració estable.        |
| **Mitjà 1 (Local)**       | NAS intern amb accés restringit                        | Permet restauració ràpida en cas d’error o pèrdua local, i és fàcil d’integrar en la xarxa.            |
| **Mitjà 2 (Extern)**      | Còpia al núvol (Google Drive / OneDrive)              | Assegura la regla del “1 fora de lloc” i protegeix davant robatori, incendi o fallada física del centre. |

### Fase 3

# Política de Còpies de Seguretat – Muntatges i Serveis Tècnics SL

## 1) Dades Objecte de Còpia

### Servidor

**Dades crítiques (còpia més freqüent):**
- Bases de dades de Comptabilitat i Clients (20 GB)  
- Còpia incremental cada 4 hores i còpia completa setmanal

**Dades importants però no crítiques:**
- Documents de Projectes (300 GB)  
- Carpetes Personals dels usuaris (100 GB)  
- Còpia incremental diària i còpia completa setmanal

### Equips Clients
- No es fa còpia completa dels 10 PCs  
- Només es protegeix la carpeta Documents dels tècnics amb còpia diària (incremental)  
- La informació rellevant es troba centralitzada al servidor  

---

## 2) Cronograma Setmanal Detallat

- **Dilluns:** BD (cada 4 h), Documents, Carpetes – Incremental – NAS  
- **Dimarts:** BD (cada 4 h), Documents, Carpetes – Incremental – NAS  
- **Dimecres:** BD (cada 4 h), Documents, Carpetes – Incremental – NAS  
- **Dijous:** BD (cada 4 h), Documents, Carpetes – Incremental – NAS  
- **Divendres:** BD (cada 4 h), Documents, Carpetes – Incremental – NAS  
- **Dissabte:** BD (cada 4 h), Documents, Carpetes – Incremental – NAS  
- **Diumenge:** Totes les dades del servidor – Completa setmanal – NAS + còpia al núvol  

**Còpia mensual:**  
- El primer diumenge de cada mes s’emmagatzema una còpia completa al núvol com a punt de retenció llarg  

---

## 3) Elecció de Mitjans i Ubicació (Regla 3-2-1)

**Mitjà 1 (Local):**  
- NAS empresarial ubicat al rack de l’empresa  
- Permet automatitzar totes les còpies incrementals i setmanals amb alta velocitat  

**Mitjà 2 (Extern):**  
- Còpia al núvol amb serveis com Azure Backup o Google Cloud Storage  
- Garanteix una còpia segura fora de l’empresa i protegeix davant incendis, robatoris o fallades totals  

**Ubicació Fora de Lloc:**  
- La còpia externa es guarda al núvol (off-site lògic)  
- La gestió i verificació de les restauracions és responsabilitat del tècnic de sistemes de l’empresa  

**Compliment de la Regla 3-2-1:**  
- 3 còpies: dades originals + NAS + Cloud  
- 2 mitjans diferents: NAS i Cloud  
- 1 còpia fora de lloc: núvol  

---

## 4) Estratègia de Recuperació (RTO/RPO)

**RPO (4 hores):**  
- Còpies incrementals de la BD cada 4 hores  
- Assegura que mai es perd més que aquest interval de treball  

**RTO (4 hores):**  
- Restauració directa des del NAS local, ràpida i accessible  
- La còpia completa setmanal + incrementals permet reconstruir l’estat de la BD sense dependències lentes  

**En cas de desastre total:**  
- Es pot restaurar des del núvol, assumint un temps extra però mantenint les dades intactes  
