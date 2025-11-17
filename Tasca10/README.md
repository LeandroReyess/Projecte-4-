# T10: Servidor impressió Linux. CUPS (tasca individual)

## Breu Descripció

### Introducció
A EverPia, busquem optimitzar els recursos dels nostres clients per reduir costos i simplificar la gestió.  
La impressió a les oficines és un punt crític: drivers incompatibles, costos de tòner descontrolats i confusió de dispositius.  

**Solució:** Implementar un **Servidor d’Impressió Centralitzat**.

---

## Cas Client: DevOptimize Solutions

- **Requisit:** Centralitzar la impressió en departaments amb clients Linux (Zorin OS) i servidors Ubuntu.  
- **Objectiu:** Mostrar una **Prova de Concepte (PoC)** abans de comprar impressores de xarxa.

---

## Escenari de Treball

- **Màquina 1 (Servidor):** Ubuntu Server  
  - Xarxa: NAT + Host-Only
- **Màquina 2 (Client):** Zorin OS Desktop  
  - Xarxa: Mateixa configuració que el servidor
- **Impressora virtual:** `cups-pdf` per simular la impressora sense hardware

---

## Prova de Concepte (PoC)

1. **Instal·lació de CUPS al servidor**
   ```bash
   sudo apt update
   sudo apt install cups

