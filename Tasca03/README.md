# 🛡️ T03 — Pla de Recuperació davant Desastres  
## Imatges del Sistema (Zorin OS 18)

## 📌 Breu Descripció
Aquesta tasca forma part del Pla de Contingència i Continuïtat del Negoci encarregat pel client.  
L’objectiu és garantir que els treballadors puguin recuperar els seus equips GNU/Linux (Zorin OS 18) de manera ràpida en cas de robatori, avaria o pèrdua total del sistema.

Per aconseguir-ho, cal estudiar eines de clonatge i creació d’imatges del sistema i elaborar una **guia tècnica operativa** per crear i restaurar imatges. En la prova de concepte s’utilitzarà **Rescuezilla**.

---

# 🟦 Introducció al Cas
El client necessita assegurar la continuïtat del negoci davant situacions catastròfiques.  
Dins del DRP (Disaster Recovery Plan), és essencial poder restaurar equips complets **sense reinstal·lar el sistema operatiu i totes les aplicacions una per una**.

Tots els equips del client utilitzen **Zorin OS 18**, amb configuracions i aplicacions específiques prèviament preparades.  
Per minimitzar temps de parada, és imprescindible comptar amb **imatges del sistema llestes per restaurar**.

---

# 🟩 Fase 1 — Anàlisi i Justificació de la Solució Tècnica

## 🎯 Objectiu
Investigar eines capaces de:
- Crear imatges completes del disc
- Restaurar-les posteriorment mantenint configuracions i aplicacions
- Treballar amb sistemes GNU/Linux
- Oferir velocitat i fiabilitat en situacions de recuperació crítica

S’ha realitzat una comparativa entre dues solucions comercials i dues de comunitat.

---

## 🧾 Comparativa d’Eines

| Tipus | Eina | Característiques destacades | Preu aproximat | Observacions |
|------|------|-----------------------------|-----------------|--------------|
| Comercial | **Acronis Cyber Protect Home Office** | Imatge completa; clonatge de disc; xifrat; còpia al núvol; restauració ràpida | 60–90€/any | Potent però orientada a entorns Windows, tot i funcionar en Linux |
| Comercial | **EaseUS Todo Backup Workstation** | Clonatge, imatges, programació; suport empreses | ~70€/any | Gran compatibilitat, però menys flexible en entorns Linux purs |
| Comunitat | **Clonezilla** | Imatges completes, suport massiu, ràpid | Gratuït | Molt potent però interfície poc amigable; requereix coneixements tècnics |
| Comunitat | **Rescuezilla** | Interfície gràfica senzilla; basat en Clonezilla; compatible amb Linux | Gratuït | Ideal per equips tècnics amb menys experiència i entorns diversos |

---

## 🏆 Proposta Final i Justificació
La solució recomanada per aquesta organització és **Rescuezilla** perquè:

- És **lliure, gratuïta i comunitària**, evitant costos recurrents.
- Està basada en **Clonezilla**, però simplificada amb interfície GUI.
- Funciona perfectament amb **GNU/Linux (Zorin OS)**.
- Permet **crear i restaurar imatges completes de manera intuïtiva**.
- Ideal per personal de manteniment que necessita rapidesa i simplicitat.
- Perfecta per un DRP on es requereix **eficiència i mínima corba d’aprenentatge**.

---

# 🟧 Fase 2 — Guia d’Ús Tècnica (Manual Operatiu)

A continuació es documenta la prova de concepte realitzada amb Rescuezilla.

## 🖥️ Entorn de Prova
- Equip base proporcionat pel client → simulat com a **màquina virtual OVA**
- Sistema operatiu: **Zorin OS 18**
- Màquina de restauració: clon idèntic sense SO
- Eina utilitzada: **Rescuezilla (Live ISO)**

---

# 📘 **Guia: Com Crear una Imatge del Sistema amb Rescuezilla**

## **1️⃣ Arrencar l’equip amb Rescuezilla**
1. Baixar ISO de Rescuezilla (pàgina oficial).
2. Crear USB bootable (Rufus, BalenaEtcher, etc.).
3. Configurar BIOS/UEFI per arrencar des de USB.
4. Triar “**Start Rescuezilla**”.

## **2️⃣ Crear la imatge**
1. Seleccionar **"Backup"**.
2. Triar el disc origen (disc on hi ha instal·lat Zorin OS 18).
3. Seleccionar destí:
   - Disc extern
   - Unitat USB
   - NAS
   - Carpeta compartida
4. Configurar opcions (compressió, fragmentació, verificació).
5. Confirmar i iniciar el procés.

📌 *Resultat:* S’obté un fitxer d’imatge amb el contingut complet del disc, incloent configuracions, aplicacions i dades.

---

# 📗 **Guia: Restauració d’una Imatge del Sistema**

## **1️⃣ Preparar la màquina de restauració**
- Nova màquina virtual idèntica (RAM, CPU, disc, xarxa)
- Disc buit sense sistema operatiu

## **2️⃣ Arrencar Rescuezilla**
Igual que en la creació de la còpia.

## **3️⃣ Restaurar la imatge**
1. Escollir l’opció **"Restore"**.
2. Seleccionar la imatge creada prèviament.
3. Escollir el disc de destinació (el nou).
4. Revisar particions i mides.
5. Confirmar la restauració.

⏱️ *Resultat estimat:* 5–25 minuts segons la mida del disc.

## **4️⃣ Reinici i validació**
- Reiniciar l’equip sense USB
- Confirmar:
  - Arrencada correcta
  - Aplicacions disponibles
  - Configuració identica a l’original

---

# 📚 Materials i Enllaços de Suport

- INCIBE — *¿Ya tienes tu Plan de Recuperación ante Desastres?*  
  https://www.incibe.es/empresas/blog/tienes-tu-plan-recuperacion-desastres  
- Rescuezilla — Pàgina oficial  
  https://rescuezilla.com

---

# ✔️ Estat de la Tasca T03
- [x] Comparativa d’eines
- [x] Solució recomanada justificada
- [x] Guia tècnica — Crear imatge del sistema
- [x] Guia tècnica — Restaurar imatge
- [ ] Incloure captures de pantalla (pendent)

---

# ✨ Autor
Document elaborat com a part de la tasca **T03 — Pla de Recuperació davant Desastres** del Projecte 4.

