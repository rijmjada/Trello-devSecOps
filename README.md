GitHub: Generar un PAT Personal Access token para obtener el repo GIT desde AWS.
GitHub: Brindar permisos de escritura al PAT, lectura, etc. al repo. Colocar el PAT en un Secret.

GitHub: Generar el CI Pipeline con GitHub Actions para el ambiente de DEV.

Debe tener los pasos ejecutados con comandos ssh desde Github actions:
(Busque la sintaxis correcta en documentación o utilice ChatGTP para obtener ayuda)
Puede utilizar este action: appleboy/ssh-action@master - name: Instalar paquetes

Comando: sudo yum install paquete

Task: Instalar paquetes Linux:

Nodejs
Npm
Git
Task: Crear directorio de trabajo en la máquina EC2, recomendamos usar /opt/nombreDeSuDirectorio. Eliminar primero el directorio si ya existe.

Task: En el directorio de trabajo creado en otra tarea ejecutar git clone. Use su token de github generado previamente como secret delante del nombre del repo:
sudo git clone https://${{ secrets.GH_TOKEN }}@github.com/usuario/repo .

Task: Instalar paquetes NPM en la Máquina Virtual

Express
Pm2
Task: Iniciar el servicio en Node Puede usar PM2 start
Task: Chequear si la aplicación está corriendo utilizando un if y un comando, puede ser curl, ns, o pm2