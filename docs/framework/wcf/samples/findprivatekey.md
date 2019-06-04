---
title: 'Ejemplo de FindPrivateKey: WCF'
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: b89d135d7412f10cb9de1e4bda1aaab14b29cbf0
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490773"
---
# <a name="findprivatekey-sample"></a>Ejemplo de FindPrivateKey

Puede ser difícil buscar la ubicación y el nombre del archivo de clave privada asociados a un certificado X.509 concreto en el almacén de certificados. La herramienta FindPrivateKey.exe facilita este proceso.

> [!IMPORTANT]
> FindPrivateKey es un ejemplo que debe compilarse antes de su uso. Consulte la [para compilar el proyecto FindPrivateKey](#to-build-the-findprivatekey-project) sección para obtener instrucciones sobre cómo compilar la herramienta FindPrivateKey.

Un administrador o cualquier usuario instala los certificados X.509 en el equipo. Sin embargo, el certificado puede tener acceso a un servicio que se ejecuta bajo una cuenta diferente. Por ejemplo, la cuenta de servicio de red.

Puede que esta cuenta no tenga acceso al archivo de clave privada porque no instaló el certificado en un principio. La herramienta FindPrivateKey le da la ubicación del archivo de clave privada de un certificado X.509 determinado. Puede agregar o quitar permisos a este archivo cuando conoce la ubicación del archivo de clave privada de los certificados X.509 determinados.

Los ejemplos que utilizan certificados para la seguridad de usan la herramienta FindPrivateKey en el *Setup.bat* archivo. Una vez que se ha encontrado el archivo de clave privada, puede usar otras herramientas como *Cacls.exe* para establecer los derechos de acceso adecuados en el archivo.

Al ejecutar un servicio de Windows Communication Foundation (WCF) en una cuenta de usuario, como una aplicación ejecutable autohospedada, asegúrese de que la cuenta de usuario tiene acceso de solo lectura al archivo. Al ejecutar un servicio WCF en Internet Information Services (IIS) las cuentas predeterminadas que se ejecuta el servicio son el servicio de red en IIS 7 y versiones anteriores o la identidad del grupo de aplicaciones en IIS 7.5 y versiones posteriores. Para obtener más información, consulte [identidades del grupo de aplicación](/iis/manage/configuring-security/application-pool-identities).

## <a name="examples"></a>Ejemplos

Al acceder a un certificado para el que el proceso no tiene privilegios de lectura, verá un mensaje de excepción similar al ejemplo siguiente:

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

Cuando esto ocurre, utilice la herramienta FindPrivateKey para buscar el archivo de clave privada y, a continuación, establezca el derecho de acceso para el proceso que se ejecuta el servicio. Por ejemplo, esto puede hacerse con la herramienta Cacls.exe tal como se muestra en el ejemplo siguiente:

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a>Para compilar el proyecto FindPrivateKey

Para descargar el proyecto, visite [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).

1. Abra el Explorador de archivos y navegue hasta la *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* carpeta en la ubicación del directorio donde instaló el ejemplo.

2. Haga doble clic en el icono del archivo .sln para abrir el archivo en Visual Studio.

3. En el **compilar** menú, seleccione **recompilar solución**.

4. Compilar la solución, genera el archivo: FindPrivateKey.exe.

## <a name="conventionscommand-line-entries"></a>Convenciones: entradas de la línea de comandos

 "[*opción*]" representa un conjunto opcional de parámetros.

 "{*opción*}" representa un conjunto de parámetros obligatorio.

 "*opción1* &#124; *opción2*" representa una opción entre los conjuntos de opciones.

 "\<*valor*>" representa un valor de parámetro que escribirse.

## <a name="usage"></a>Uso

```
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

Dónde:

```
       <subjectName> The subject name of the certificate
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)
       -f            output file name only
       -d            output directory only
       -a            output absolute file name
```

Si se especifica ningún parámetro en el símbolo del sistema, se muestra este texto de ayuda.

## <a name="examples"></a>Ejemplos

Este ejemplo busca el nombre de archivo del certificado con un nombre de sujeto de "CN = localhost", en el almacén Personal del usuario actual.

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

Este ejemplo busca el nombre de archivo del certificado con un nombre de sujeto de "CN = localhost", en el perfil Personal almacenar del usuario actual y la ruta de acceso completa del directorio de salida.

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

Este ejemplo busca el nombre de archivo del certificado con una huella digital de "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", en el almacén personal del equipo local.

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
