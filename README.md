Wildfly



Podemos cambiar de puerto :)






nombre VM: jenkinsv2
jenkins - descargar war el segundo: https://jenkins.io/download/
sh glassfish:https://github.com/Yosemir/sh 

entrar como su: sudo su
pegar el repositorio:git clone https://github.com/Yosemir/sh.git
entrar carpeta: cd sh
ejecutar sh: sh install_wildfly.sh
cuando sale Started 315: dar enter
liberar puertos: 8080 y 9990
usuario y pass: admin
subir war y ingresar al war: jenkins
salimos del home hasta ver la carpeta root con ls: cd ../../..
ejecutamos lo que nos da jenkins: cat /root/.jenkins/secrets/initialAdminPassword
nos dara un codigo y lo copiamos y pegamos.
le damos click al primero.
nos pide un registros todo admin.
continuar
le damos en el boton star.
instalamos maven en ubuntu. 3ro linuxize.
instalamos el plugin, Blue Ocean y le damos instalar sin reiniciar.
volvemos al inicio y abrimos el open Blue Ocean
le damos en create new pipelin
ingresamos en github, developer setings y personal access token y le damos en generate new token.
cualquier nombre y seleccionamos todo y copiamos el token.
en el pipeline seleccionamos github y pegamos el token.
seleccionamos valle grande y el proyecto.
entramos y creamos los pasos de despliegue (build,test)
	build (mvn clean package)
	test (mvn test)
y le damos en restart build.
inngresamos al depliegue de bluild y donde limpia y bajamos del todo y copiamos el directorio del war ejemplo: 
/root/.jenkins/workspace/AS2016S5_CAME_Dev/target/Came.war
creamos el deploy
cp /root/.jenkins/workspace/AS2016S5_CAME_Dev/target/Came.war /opt/wildfly/standalone/deployments /opt/wildfly/standalone/deployments (Por defecto)
ingresamos al war
