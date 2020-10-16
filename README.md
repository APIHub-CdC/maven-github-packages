# maven-github-packages

A continuación, se muestra el proceso de configuración para instalar los paquetes (dependencias maven) de Api HUB.

## Requisitos

1. Java >= 1.7
2. Maven >= 3.3
3. Cuenta de GitHub

## Generar token de acceso personal

 1. Iniciar sesión con su cuenta de GitHub.

 2. En la esquina superior derecha de cualquier página, haz clic en tu foto de perfil y luego en **Settings**.
    <p align="center">
        <img src="https://github.com/APIHub-CdC/imagenes-cdc/blob/master/maven/01_Settings.png" width="268">
    </p>
 
 3. En la barra lateral izquierda, haz clic en **Developer settings**.
 
    <p align="center">
        <img src="https://github.com/APIHub-CdC/imagenes-cdc/blob/master/maven/02_Developer_Settings.png" width="268">
    </p>
    
## Generar token de acceso personal

 1. Iniciar sesión con su cuenta de GitHub.

**Opcional**: Si desea cifrar su contenedor, coloque una contraseña en una variable de ambiente.

```shell
export KEY_PASSWORD=your_super_secure_password
```

## Instalar el paquete de los repositorios

Teniendo las configuraciones anteriores ya solo falta instalar los paquetes (dependencias), con el siguiente comando:

> **NOTA:** La configuracion del archivo settingsAPIHUB.xml, puede ser integrada en el **settings.xml** del **.m2**, si esto se realiza, quitar el comando *--settings settingsAPIHUB.xml* se la siguiente instrucción

```shell
mvn --settings settingsAPIHUB.xml clean install -Dmaven.test.skip=true
```
