---
title: "FindPrivateKey | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "FindPrivateKey"
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# FindPrivateKey
Puede ser difícil buscar la ubicación y el nombre del archivo de clave privada asociados a un certificado X.509 concreto en el almacén de certificados.La herramienta FindPrivateKey.exe facilita este proceso.  
  
> [!IMPORTANT]
>  FindPrivateKey es un ejemplo que debe compilarse antes de su uso.Vea la sección “Para compilar el proyecto FindPrivateKey” más abajo para obtener instrucciones sobre cómo compilar la herramienta FindPrivateKey.  
  
 Un administrador o cualquier usuario instala los certificados X.509 en el equipo.Sin embargo, se puede tener acceso al certificado mediante un servicio que se ejecuta bajo una cuenta diferente \(por ejemplo, ASPNET en [!INCLUDE[wxp](../../../../includes/wxp-md.md)] o las cuentas del SERVICIO DE RED en [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]\).  
  
 Puede que esta cuenta no tenga acceso al archivo de clave privada porque no instaló el certificado en un principio.La herramienta FindPrivateKey le da la ubicación del archivo de clave privada de un certificado X.509 determinado.Puede agregar o quitar permisos a este archivo cuando conoce la ubicación del archivo de clave privada de los certificados X.509 determinados.  
  
 Los ejemplos que utilizan certificados para la seguridad utilizan la herramienta FindPrivateKey en el archivo Setup.bat.Una vez que se ha encontrado el archivo de clave privada, puede usar otras herramientas como Cacls.exe para establecer los derechos de acceso adecuados en el archivo.  
  
 Cuando se ejecuta un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bajo una cuenta de usuario, como una aplicación ejecutable autohospedada, asegúrese de que la cuenta de usuario tiene acceso de solo lectura al archivo.Al ejecutar un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bajo Internet Information Services \(IIS\), las cuentas predeterminadas que el servicio ejecuta son ASPNET en [!INCLUDE[wxp](../../../../includes/wxp-md.md)] o el SERVICIO DE RED en [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], que no tiene acceso al archivo de clave privada de manera predeterminada.  
  
## Ejemplos  
 Al tener acceso a un certificado para el que el proceso no tiene privilegio de lectura, ve un mensaje de excepción similar al siguiente ejemplo.  
  
```  
System.ArgumentException was unhandled  
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."  
Source="System.ServiceModel"  
```  
  
 Cuando esto se produce, utilice la herramienta FindPrivateKey para buscar el archivo de clave privada y, a continuación, establezca el derecho de acceso para el proceso bajo el que el servicio se está ejecutando.Por ejemplo, esto se puede hacer con la herramienta Cacls.exe, tal y como se muestra en el ejemplo siguiente.  
  
```  
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
```  
  
#### Para compilar el proyecto FindPrivateKey  
  
1.  Abra el [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] y navegue hasta el subdirectorio específico del lenguaje bajo la ubicación del directorio donde instaló el ejemplo.  
  
2.  Haga doble clic en el icono del archivo .sln para abrir el archivo en Visual Studio.  
  
3.  En el menú **Compilar**, seleccione **Recompilar solución**.Los archivos del programa cliente se compilan en client\\bin y los archivos de programa de servicio se compilan en service\\bin.  
  
4.  Al compilar la solución, se crea el archivo: FindPrivateKey.exe.  
  
## Convenciones: entradas de la línea de comandos  
 "\[*option*\]" representa un conjunto opcional de parámetros.  
  
 "{*option*}" representa un conjunto obligatorio de parámetros.  
  
 "*option1* &#124; *option2*" representa una opción entre los conjuntos de opciones.  
  
 "\<*value*\>" representa un valor de parámetro que se va a escribir.  
  
## Uso  
  
```  
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]  
```  
  
 Dónde:  
  
```  
       <subjectName> The subject name of the certificate  
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)  
       -f            output file name only  
       -d            output directory only  
       -a            output absolute file name  
```  
  
 Si no se especifica ningún parámetro en el símbolo del sistema, se mostrará este texto de ayuda.  
  
## Ejemplos  
 Este ejemplo busca el nombre de archivo del certificado con un nombre de asunto de "CN\=localhost", en el almacén personal de Current User.FindPrivateKey My CurrentUser \-n "CN\=localhost".  
  
 Este ejemplo busca el nombre de archivo del certificado con un nombre de asunto de "CN\=localhost", en el almacén personal del usuario actual y proporciona la ruta de acceso completa al directorio.  
  
```  
User.FindPrivateKey My CurrentUser -n "CN=localhost" -a  
  
```  
  
 Este ejemplo busca el nombre de archivo del certificado con una huella digital de "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", en el almacén personal del equipo local.  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –c  
```  
  
## Vea también