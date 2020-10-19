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
        <img src="https://github.com/APIHub-CdC/imagenes-cdc/blob/master/maven/01_Settings.png" width="150">
    </p>
 
 3. En la barra lateral izquierda, haz clic en **Developer settings**.
 
    <p align="center">
        <img src="https://github.com/APIHub-CdC/imagenes-cdc/blob/master/maven/02_Developer_Settings.png" width="200">
    </p>
    
 4. En la barra lateral izquierda, haz clic en **Personal access tokens**.
 
    <p align="center">
        <img src="https://github.com/APIHub-CdC/imagenes-cdc/blob/master/maven/03_Personal_Access_Tokens.png" width="200">
    </p>

 6. Haz clic en **Generate new token**.

    <p align="center">
        <img src="https://github.com/APIHub-CdC/imagenes-cdc/blob/master/maven/04_Generate_New_token.png" width="510">
    </p>
    
 7. Dale a tu token un nombre descriptivo y seleccione los ámbitos o permisos que le gustaría otorgar a este token. Para usar su token para acceder a los repositorios desde la línea de comando, seleccione **repo** y **write:packages**.

    <p align="center">
        <img src="https://github.com/APIHub-CdC/imagenes-cdc/blob/master/maven/05_Form_Generate_Token.png" width="500">
    </p>
    
 8. Haz clic en **Generate token**.

    <p align="center">
        <img src="https://github.com/APIHub-CdC/imagenes-cdc/blob/master/maven/06_Button_Generate_Token.png" width="150">
    </p>
    
 9. Copia el token a su portapapeles. Por razones de seguridad, después de salir de la página, no podrá volver a ver el token..

    <p align="center">
        <img src="https://github.com/APIHub-CdC/imagenes-cdc/blob/master/maven/07_Copy_token.png" width="480">
    </p>
 

## Agregar las credenciales de acceso

 1. Iniciar sesión con su cuenta de GitHub.

**Opcional**: Si desea cifrar su contenedor, coloque una contraseña en una variable de ambiente.

```shell
export KEY_PASSWORD=your_super_secure_password
```
2. Agregar las credenciales de acceso al archivo **settingsAPIHUB.xml**


## Instalar el paquete de los repositorios

Teniendo las configuraciones anteriores ya solo falta instalar los paquetes (dependencias), con el siguiente comando:

> **NOTA:** La configuracion del archivo **settingsAPIHUB.xml**, puede ser integrada en el **settings.xml** del **.m2**, si esto se realiza, quitar el comando *--settings settingsAPIHUB.xml* se la siguiente instrucción

```shell
mvn --settings settingsAPIHUB.xml clean install -Dmaven.test.skip=true
```
