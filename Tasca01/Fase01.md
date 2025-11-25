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

