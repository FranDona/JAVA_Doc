# JAVA_Doc
--------------

[//]: # (version: 1.0)
[//]: # (author: Fran Dona)
[//]: # (date: 2024-03-12)



# Tabla de contenidos
- [JAVA\_Doc](#java_doc)
- [Tabla de contenidos](#tabla-de-contenidos)
  - [¿Qué es Java?](#qué-es-java)
  - [Instalacion de Java](#instalacion-de-java)
    - [Opcion OpenJDK](#opcion-openjdk)
    - [Opcion Oracle](#opcion-oracle)



## ¿Qué es Java?
Java es un lenguaje de programación de propósito general conocido por su portabilidad, seguridad y capacidad para desarrollar aplicaciones robustas y escalables. Se destaca por su orientación a objetos, soporte para programación multi-hilo y amplio ecosistema de herramientas y frameworks.

## Instalacion de Java
### Opcion OpenJDK
```bash
# Instalar el JRE
sudo apt install default-jre
# Instalar el JDK
sudo apt install default-jdk
# Verificar la instalación
java -version
javac -version
```

### Opcion Oracle
```bash
cd Descargas
wget https://download.oracle.com/java/17/latest/jdk-17_linux-x64_bin.deb
sudo apt install ./jdk-17_linux-x64_bin.deb

# Si queremos alternar entre Java Oficial y OpenJDK:
sudo update-alternatives --config java
sudo update-alternatives --config javac
```

----
```bash
## Configurar variable de entorno
# Volvemos a ejecutar el comando de selección de JDKs
sudo update-alternatives --config java

# Copiamos la salida por defecto
# * 0  /usr/lib/jvm/jdk-17oracle-x64/bin/java      
# Editamos el archivo de configuración de entorno del sistema
sudo nano /etc/environment
# Metemos en la linea siguiente lo copiado menos el /bin/java
JAVA_HOME="/usr/lib/jvm/jdk-17-oracle-x64"
# CTRL + O, para guardar!
# CTRL + X, salir!

# Recargamos el archivo en la sesión actual
source /etc/environment
# Y vemos el valor de la variable
echo $JAVA_HOME
```

Damos permisos de escritura y ejecución a los ejecutables de Java

```bash
cd /usr/lib/jvm/jdk-17-oracle-x64/bin
sudo chmod a+x java  
sudo chmod a+x javac 
```