# 🔐 T05 — Accés Remot: Connexió via SSH  

## 📌 Breu Descripció
Aquesta tasca té com a objectiu establir una **prova de concepte (PoC)** per a l’accés remot segur mitjançant **SSH (Secure Shell)**.  
L’objectiu és que futurs becaris puguin connectar-se de manera segura als nostres servidors i equips clients sense necessitat de suport continu.

---

# 🟦 Introducció a SSH

**SSH** és l’estàndard de la indústria per a connexions remotes segures. Permet:
- Administrar servidors Linux (i Windows amb OpenSSH habilitat)  
- Xifrar tota la comunicació  
- Transferir fitxers de manera segura  
- Automatitzar tasques remotament  

Avantatges:
- Connexió **segura i fiable**  
- Ús d’autenticació amb **usuari/contrassenya** o **clau pública/privada**  
- Funciona tant des de terminals Linux com Windows

---

# 🟩 Configuració i Connexió SSH

## 1️⃣ Preparació del Servidor
1. Assegura’t que el servidor té **SSH habilitat**.
   ```bash
   sudo systemctl status ssh

