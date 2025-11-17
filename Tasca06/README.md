# 🖥️ T06 — Accés remot: Escriptori remot (RDP)

## 📌 Breu Descripció
Aquesta tasca té com a objectiu establir una **prova de concepte (PoC)** per a l’accés remot amb **interfície gràfica**.  
És especialment útil quan cal donar suport a equips Windows amb aplicacions gràfiques o quan l’usuari necessita assistència directa.  

---

# 🟦 Introducció a RDP

**RDP (Remote Desktop Protocol)** és el protocol de Microsoft per accedir a escriptoris remots.  
Actualment:
- Funciona amb **Windows Server i Windows 11/10**.  
- Algunes distribucions Linux modernes (com Zorin OS amb Gnome) permeten connexions RDP.  
- Permet controlar el ratolí i el teclat de l’equip remot.  

Avantatges:
- Suport complet d’entorn gràfic  
- Transferència segura de la sessió  
- Ideal per assistència directa a clients o administració remota  

---

# 🟩 Configuració i Connexió RDP

## 1️⃣ Preparació del Servidor Windows
1. Activa **Escriptori Remot**:
   - Windows 11: Configuració → Sistema → Escriptori remot → Activa “Habilita Escriptori remot”.
2. Confirma l’adreça IP de l’equip:
   ```powershell
   ipconfig

