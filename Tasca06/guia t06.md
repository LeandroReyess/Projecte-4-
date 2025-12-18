**T06: Accés Remot — Escriptori Remot (RDP) (tasca individual)**

**Configuració de la màquina Windows**

Per dur a terme aquesta activitat caldrà disposar de dues màquines virtuals. La primera serà una màquina amb sistema operatiu Windows i la segona una màquina amb Zorin OS.

Un cop creades les dues màquines, el primer pas serà afegir un segon adaptador de xarxa. En aquest cas, es configurarà en mode *host-only* a totes dues màquines.

Després d’aquesta configuració inicial, començarem treballant amb la màquina Windows. El següent pas consistirà a cercar i accedir a l’opció de Configuració de l’Escriptori Remot per continuar amb el procés.

![image1](image1.png)

Un cop dins del menú corresponent, caldrà activar l’opció d’**Escriptori Remot**.

Aquesta configuració és necessària per poder establir una connexió remota amb la màquina Windows.

![image2](image2.png)

**Configuració de la màquina Zorin**

Un cop finalitzada la configuració de la màquina Windows, continuarem amb la preparació de la màquina Zorin.

Seguidament, accedirem al menú de **Configuració** per activar l’escriptori remot. Per fer-ho, primer haurem d’entrar a l’apartat de **Sistema** dins de la configuració.

![image3](image3.png)

Un cop a dins, procedirem a configurar l’escriptori remot. Per començar, serà necessari activar les dues primeres opcions disponibles. Finalment, el sistema ens sol·licitarà un nom d’usuari i una contrasenya, on podrem introduir les credencials que vulguem. En aquest cas, s’utilitzarà la mateixa contrasenya que la de l’usuari.

![image4](image4.png)

Un cop tinguem les dues màquines correctament configurades, el pas següent serà establir la connexió entre elles.

**Connexió des de la màquina Windows cap a la màquina Zorin**

Per establir la connexió amb la màquina Zorin des de Windows, utilitzarem l’eina **Connexió a l’Escriptori Remot**, que ve integrada per defecte al sistema operatiu Windows.

![image5](image5.png)

Un cop oberta l’eina, haurem d’introduir l’adreça IP de la màquina Zorin. Per conèixer aquesta IP, executarem l’ordre `ip a` des de la terminal de la màquina Zorin.

![image6](image6.png)
Un cop dins ens demana les credencials

![image7](image7.png)

A continuació apareixerà una finestra d’advertiment relacionada amb el certificat, la qual haurem d’acceptar per poder continuar amb el procés.

![image8](image8.png)

Un cop completats tots aquests passos, podrem comprovar que ja hem accedit correctament a la màquina Zorin.

![image9](image9.png)

**Connexió des de la màquina Zorin cap a la màquina Windows**

Seguidament establirem la connexió des de la màquina Zorin cap a la màquina Windows. Per fer-ho, utilitzarem l’eina **Remmina**, que ja ve preinstal·lada en Zorin.

![image10](image10.png)

Un cop oberta l’eina Remmina, haurem d’introduir l’adreça IP de la màquina Windows. Per obtenir aquesta IP, accedirem a **PowerShell** a Windows i executarem l’ordre `ipconfig`.

![image11](image11.png)

Tot seguit apareixerà una finestra d’advertiment sobre el certificat, que haurem d’acceptar per poder continuar amb la connexió.

![image12](image12.png)

Un cop completats aquests passos, el sistema ens sol·licitarà les credencials de l’usuari.

![image13](image13.png)

Un cop realitzats tots aquests passos, podrem comprovar que hem accedit correctament a la màquina Windows.

![image14](image14.png)
