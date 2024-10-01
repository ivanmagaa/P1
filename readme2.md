
PRÁCTICA 1 - Guía de Comandos de Docker


##1. Descargar unha imaxe de Docker e comprobala no teu equipo

O primeiro paso é descargar unha imaxe de Ubuntu desde Docker Hub ao teu equipo. Unha imaxe en Docker é unha plantilla que contén o sistema operativo e as aplicacións necesarias para crear un contedor.

Comando para descargar a imaxe de Ubuntu:

**docker pull ubuntu**

Comprobar se a imaxe foi descargada:

**docker images**

Este comando amosa unha lista de todas as imaxes dispoñibles no teu equipo, incluíndo a imaxe de Ubuntu que acabas de descargar.

---

##2. Crear un contedor sen nome, está arrincado?, cómo obtés o nome?


Cando creas un contedor, Docker pode asignarlle un nome automático. Neste paso, lanzamos un contedor sen especificar nome revisamos se está en execución.

Comando para crear un contedor sen nome:

**docker run -d ubuntu**

Comprobar se o contedor está arrincado:

**docker ps**

Este comando lista todos os contedores en execución. Aquí verás un contedor con nome asignado
automaticamente por Docker.

---

##3. Crear un contedor co nome 'u1' e acceder a el

Agora imos crear un contedor de Ubuntu, pero esta vez dándolle un nome específico. Despois, accederemos ao contedor para interactuar co sistema operativo desde dentro.

Comando para crear un contedor co nome 'u1':

**docker run -d --name u1 ubuntu**

Acceder ao contedor 'u1':

**docker exec -it u1 bash**

O comando exec permite executar un comando dentro dun contedor en execución. O parámetro -it abre unha interface de terminal interactiva, e bash executa o shell de Ubuntu no contedor.

---

##4. Comprobar a IP do contedor e facer ping a google.com

Dentro do contedor, podemos comprobar a súa dirección IP e realizar probas de conectividade, como facer ping a Google.

Comando para ver a IP do contedor 'u1':

**docker inspect u1 | grep "IPAddress"**

Facer ping a Google dentro do contedor:

**ping google.com**

Este comando proba a conectividade desde o contedor á rede externa.

---

##5. Crear un contedor chamado 'bono' e comprobar se se pode facer ping entre contedores

Neste paso, crearás outro contedor chamado 'bono' e verás se é posible facer ping entre os dous contedores.

Crear un contedor chamado 'bono':

**docker run -d --name bono ubuntu**

Obter a IP de 'bono' para facer ping desde 'u1':

**docker inspect bono | grep "IPAddress"**

Facer ping entre os contedores:

Primeiro, accede ao contedor 'u1':

**docker exec -it u1 bash**

Logo, fai ping á IP do contedor 'bono':

**ping <IP_de_bono>**

---

##6. Que pasa co contedor se pechas a terminal?

Se lanzas o contedor en modo detach (-d), este seguirá executándose aínda que peches a terminal.

Podes comprobar o estado de calquera contedor en execución.
Comprobar o estado do contedor:

**docker ps**

Este comando lista os contedores que seguen arrincados.

---

##7. Canto espazo no disco ocupaches?

Docker permite ver canto espazo ocupan as imaxes, contedores e volumes. Podes usar o comando docker system df para calcular o uso total de disco.
Comando para ver o uso de disco:

**docker system df**

Este comando amosa un resumo do uso de disco para todos os recursos de Docker.

---

##8. Canto RAM ocupan os contedores?

Para ver a cantidade de memoria RAM usada polos contedores, usa o comando docker stats, que proporciona unha monitorización en tempo real.
Comando para ver o uso de RAM:

**docker stats**

---

##9. Clonar o repositorio

Se queres traballar cun repositorio de GitHub no teu equipo, o primeiro que debes facer é clonar ese repositorio.

Comando para clonar un repositorio:

**git clone /https://github.com/ivanmagaa/P1.git**

---

##10. Engadir o arquivo readme2.md

Para engadir un novo arquivo ao repositorio, primeiro créao localmente e logo engádeo ao sistema de control de versións.

**git add readme2.md**

---

##11. Subir os cambios ao repositorio remoto

Unha vez engadidos os cambios, deberás realizar un commit e logo subilos ao repositorio remoto.

Realizar un commit:

**git commit**

Subir os cambios ao repositorio remoto:

**git push**


##12. Comprobar as diferencias entre o repositorio local e remoto

É importante verificar se hai diferencias entre o teu repositorio local e o remoto antes de realizar cambios ou actualizacións.

Comprobar se hai cambios no remoto:

**git fetch**


