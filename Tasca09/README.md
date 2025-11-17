# T09: Servidor fitxers Linux. NFS (tasca individual)

## Breu Descripció

### Introducció
Molt bé, equip de consultors júniors.  
En aquest projecte ens trobem amb un requisit molt habitual dels nostres clients: **centralització de dades en entorns Linux**.

---

## Cas Client: DevOptimize Solutions

- **Tipus de client:** Startup de desenvolupament de programari Linux-only.  
- **Problema:** Codi font i actius (documents, scripts) descontrolats; cada desenvolupador treballa amb còpies locals.  
- **Impacte:** Errors de versió constants i pèrdua d’eficiència.  
- **Solució requerida:** Servidor de fitxers centralitzat sense autenticació centralitzada per ara.  

---

## Objectiu de la Tasca

Implementar un **servidor NFS (NFSv3)** i un **client Linux** que consumeixi els recursos compartits.  

### Tasques principals:

1. Crear un servidor NFS.
2. Configurar un client Linux que accedeixi als recursos del servidor.
3. Crear **usuaris i grups** per simular l’entorn real del client.
4. Configurar **control d’accés** amb:
   - Opcions d’exportació a `/etc/exports`
   - Permisos del sistema de fitxers (`chmod`, `chown`)
5. Demostrar la correcta funcionalitat amb diferents usuaris i grups.

---

## Recursos i Materials

- Repositori amb descripció completa: [Projecte04-NFS](https://github.com/SMX2n/Projecte04-NFS)  
- **Material del curs:** UD5. AA1. NFS (Moodle del mòdul de Sistemes Operatius en Xarxa)  
- Tutorials externs:  
  - Ruiz, P. (2021, novembre 22). *NFS (parte 1): Instalación en un servidor Ubuntu 20.04 LTS.* [Link](https://somebooks.es/nfs-parte-1-instalacion-en-un-servidor-ubuntu-20-04-lts/)  
  - Ruiz, P. (2021, desembre 2). *NFS (parte 2): Instalación en un cliente Ubuntu 20.04 LTS.* [Link](https://somebooks.es/nfs-parte-2-instalacion-en-un-cliente-ubuntu-20-04-lts/)  
  - Ubuntu Server Documentation: *Network File System (NFS)* [Link](https://documentation.ubuntu.com/server/how-to/networking/install-nfs/)

---

## Notes Importants

- La tasca serveix per demostrar **com quedarà la solució proposada al client**.  
- És important evidenciar les **limitacions** de treballar sense autenticació centralitzada.  
- Cal fer proves amb **diversos usuaris i grups** per validar els permisos i el control d’accés.

