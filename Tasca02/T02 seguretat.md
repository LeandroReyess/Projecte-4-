Per comneçar el primer pas sera tindre una maquina client windows amb un disc principal on tindrem el sistema operatiu i despres un segon disc de 10 Gb en el qual farem la copia.

![Image1](Image1.png)

Un cop fet això el seguent pas sera inicialitzar el disc, per fer això el primer pas sera inicar la maquina i obrir l'administrador de disc.  
Un cop fet això el que farem sera crear un volum simple en el disc, per fer-ho hem de fer click dret sobre el disc i escollirem la opcio de "Nuevo volumen simple"  
Un cop fet això s'obrira una finestra en la qual unicament farem siguiente siguiente fins que tinguem el volum creat i es vegi tal i aixì

![Image2](Image2.png)

Seleccionem on volem instalar windows.

![Image3](Image3.png)

El seguent pas sera instalar duplicati, per fer això anirem al seguent enllaç

[Link de descarrega](https://duplicati.com/download)

Instalarem la versio per el nostre equip, en aquest cas instalarem la versió per windows

![Image4](Image4.png)

Un cop que tinguem instalat el archiu.exe l'executarem i farem siguiente siguiente, aceptant els termes neccesaris fins que tinguem el duplicati instalat correctament

![Image5](Image5.png)

Un cop instalat, s'obrira una pestanya en el nostre navegador en el qual ens demanara que escollim una constrasenya per fer servir duplicati.

En la qual podem escollir qualsevol contrasenya ja que sera personal, important no olvidar-la

![Image6](Image6.png)

Un cop que ja tenim el duplicati, crearem alguns documents de proba per poder fer la copia de segureta  

![Image7](Image7.png)

El seguent pas sera configurar les copies de seguretat que voldrem, aixi que começarem escollint la opcio de backup add i add new backup,

Un cop aqui haurem de colocar les dades de la nostra copia

![Image8](Image8.png)

El seguent pas sera escollir on tindrem guardada la copia, en aquest cas la guardarem en el nostre cas la guardarem en el disc secundari  

![Image9](Image9.png)

Un cop fet això hem d'escollir quins documents volem fer la copia  

![Image10](Image10.png)

Tot seguit haurem d'escollir cada quan de temps volem que és realitzi la copia, en aquest cas la farem cada 1 hora  

![Image11](Image11.png)

Un cop que arribem aqui escollirem les opcions que en demani i un cop fet, ja tindrem la nostra copia creada 

![Image12](Image12.png)

El proxim pas sera fer el mateix però amb l'unic canvi que farem la copia en el nuvol, en aquest cas farem servir el google drive, per fer-ho farem el seguent però unicament modificarem el seguent.

El lloc en el qual guardarem la copia, en la qual haurem de vincular la conta, per fer això farem click a AuthID

![Image13](Image13.png)

L'altre cosa que haurem d'editar sera cada quan és fa la copia, en aquest cas sera cada dia a las 6 de la tarda

![Image14](Image14.png)

Un cop fet aixo ja tindrem les dues copies creades

![Image15](Image15.png)

El seguent pas que farem sera borrar els documents de proba per poder comprobar que podem recuperar la copia correctament  

![Image16](Image16.png)

Un cop que ja hem borrat els documents, el seguent pas sera recuperar la copia, per poder fer això anirem a "Restores" i farem click a "Start"

Escollirem la copia que volem restaurar, en aquest cas prova

![Image17](Image17.png)

escollirem els fitxers que volem restaurar, en aquest cas la carpeta documents

![Image18](Image18.png)

Farem siguiente siguiente i un cop fet això ja tindrem feta la restauració

![Image19](Image19.png)

![Image20](Image20.png)

Per poder restaurar la copia que hem fet a google drive ho farem igual però selecionarem l'altre copia

---

**Part 2: Còpia seguretat servidor Linux**

Per poder començar haurem de tindre una maquina linux, en aquest cas farem servir una maquina ubuntu server per realitzar la prova.

El primer pas sera tindre la maquina actualitzada per tant farem

sudo apt update && sudo apt upgrade \-y

Farem servir el Duplicity per poder fer copies en local i en remot.

Per començar haurem de tindre un disc secundari, en aquest cas farem servir un disc de 10 Gb

Un cop que ja tenim el disc, el primer pas sera donar-li un format, li donarem el format xfs i muntarem al disc a la ruta /media/backup com que aquesta ruta no existeix, el primer pas sera crear la ruta, això ho farem de la seguent forma

mkdir /media/backup

![Image21](Image21.png)

Un cop fet això haurem de donar-li format al disc, això ho farem amb l'eina fdisk, per tant el primer pas sera

sudo apt install fdisk

Un cop fet això farem fdisk \-l per veure el disc que tenim

fdisk \-l

![Image22](Image22.png)

Podem veure que el segon disc esta, per tant el seguent pas sera crear el seu volum, per fer això farem servir la comanda pvcreate, per poder fer servir aquesta comanda primer haurem d'instalar lvm2

sudo apt install lvm2

Un cop fet això ja podrem crear el volum en aquest cas sera amb la seguent comanda

pvcreate /dev/sdb

![Image23](Image23.png)

Un cop que ja tenim el volum muntat el seguent pas sera formategar-lo amb la seguent comanda

mkfs.xfs \-f /dev/sdb

![Image24](Image24.png)

Per ultim tocara muntar el disc a la carpeta que hem crear previament, per fer axò farem la seguent comanda

mount /dev/sdb /media/backup

![Image25](Image25.png)

Un cop que ja tenim el disc muntat el seguent pas sera instalar Duplicity

apt install duplicity \-y

Un cop fet això el seguent pas sera crear un parell d’usuaris amb carpeta personal i crear 4 arxius de 10 MB a la carpeta home del teu usuari.

per fer això ho farem de la seguent forma

useradd \-m \-s /bin/bash user1

useradd \-m \-s /bin/bash user2

![Image26](Image26.png)

fallocate \-l 10MB file1  
fallocate \-l 10MB file2  
fallocate \-l 10MB file3  
fallocate \-l 10MB file4

![Image27](Image27.png)

Un cop que ja tenim els arxius de prova creats els seguent pas sera fer la copia de seguretat, això ho farem amb el duplicity

La comanda per fer una copia de seguretat completa de la carpeta home sera la seguent

duplicity full /home/user file:///media/backup/

En el moment en que ens demana el passphrase podem escollir el que nosaltres volguem, ja que és una prova en el meu cas he escollit copia

![Image28](Image28.png)

Podem veure que la copia s'ha creat correctament en el disc secundari, això amb la comanda ls

![Image29](Image29.png)

Un cop fet això el seguent pas sera esborrar els arxius i comprobar que funcionen correctament

![Image30](Image30.png)

Un cop que ja no estan els arxius farem servir la copia per recuperar-los, en aquest cas guardarem la copia dins d'una carpeta que es diu copia dins de la carpeta /home/user això ho farem amb la seguent comanda:

duplicity restore file:///media/backup/ /home/user/copia

![Image31](Image31.png)
