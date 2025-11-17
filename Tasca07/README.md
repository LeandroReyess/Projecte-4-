# T07: Accés remot. Serveis d’assistència remota (tasca en parelles)

## Breu Descripció
Fins ara hem vist eines per administrar servidors (SSH, RDP, VNC).  
A EverPia, una gran part del temps de treball prové del suport directe a l’usuari final (Helpdesk).  

Quan un client té incidències com:
- "El PDF no s'obre"
- "Ha desaparegut una icona"
- "La impressora no imprimeix"

no podem demanar configuracions complexes com VPN o obrir ports de router. Per això necessitem eines d’assistència remota sota demanda: ràpides, fiables, segures i funcionals fins i tot en xarxes restrictives.

La direcció ha decidit estandarditzar l’eina oficial per a aquestes tasques. La missió és:
1. Analitzar el mercat.
2. Proposar la millor solució.
3. Crear la documentació per a tècnics i clients.

---

## Fase 1: Anàlisi Comparativa i Selecció de la Solució

### Tasques
1. Investigar quatre eines d’assistència remota:
   - **Obligatori:** TeamViewer, AnyDesk, Google Remote Desktop.
   - **Opcional:** Una quarta eina a triar (ex. RustDesk, Zoho Assist, etc.).

2. Crear una taula comparativa amb els següents criteris:

| Eina                  | Facilitat d’ús (per al client) | Disponibilitat (SO) | Model de Preu / Llicència |
|-----------------------|--------------------------------|-------------------|---------------------------|
| TeamViewer            | Portable, fàcil d’usar, ID simple | Windows, macOS, Linux, Mobile | Gratis personal, llicència tècnica ~€35/mes |
| AnyDesk               | Instal·lació opcional, ID ràpid | Windows, macOS, Linux, Mobile | Gratis personal, llicència tècnica ~€10/mes |
| Google Remote Desktop | Sense instal·lació complexa, vinculació Google | Windows, macOS, Linux, Chrome OS | Gratuït |
| RustDesk (ex.)        | Portable, codi obert, senzill | Windows, macOS, Linux, Mobile | Gratuït / self-hosted |

3. Recomanació:  
   Basant-vos en la taula, escollir l’eina més equilibrada entre facilitat, funcionalitat i cost, i justificar la decisió.

---

## Fase 2: Creació de les Guies d'Ús (Documentació)

### Guia 1: Manual per al Tècnic (Intern)
Dirigit a futurs tècnics i becaris:

- **Instal·lació:** Versió completa/tècnica.
- **Inici de sessió:** Com iniciar la sessió de suport remot.
- **Gestió de funcions clau:** Transferència d’arxius, canvi de pantalla, reinici remot.
- **Bones pràctiques de seguretat:** Tancar sessions, no desar contrasenyes de clients.

> Incloure captures de pantalla de cada pas significatiu.

---

### Guia 2: Manual per al Client (Usuari Final)
Dirigit a clients amb incidències:

- **Descàrrega:** Enllaç o mòdul "Quick Support" sense necessitat d’instal·lació.
- **Execució:** On fer clic exactament.
- **Identificació de sessió:** Com comunicar ID i contrasenya al tècnic.
- **Acceptació:** Com aprovar la connexió remota.

> Guia molt visual i senzilla, amb captures de pantalla clares.

---

## Materials i Links de Suport
- [Soporte remoto para amigos/familiares](https://www.genbeta.com/a-fondo/que-software-instalar-a-tus-familiares-amigos-para-darles-soporte-ayuda-remoto)
- [Alternatives a TeamViewer](https://www.genbeta.com/herramientas/necesitas-escritorio-remoto-puedes-decirle-adios-a-teamviewer-rustdesk-gratis-e-ideal-para-usar-pc-movil)
- [Chrome Remote Desktop](https://www.genbeta.com/herramientas/chrome-remote-desktop-que-como-funciona-como-puedes-usarlo-para-controlar-tu-pc-forma-remota)

