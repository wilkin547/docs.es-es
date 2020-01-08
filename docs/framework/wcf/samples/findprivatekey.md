---
title: Ejemplo de FindPrivateKey
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: 0ed1e5e81a5d2f7f3586e5dce306e8244b5ebd48
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346018"
---
# <a name="findprivatekey-sample"></a>Ejemplo de FindPrivateKey

Puede ser difícil buscar la ubicación y el nombre del archivo de clave privada asociados a un certificado X.509 concreto en el almacén de certificados. La herramienta FindPrivateKey.exe facilita este proceso.

> [!IMPORTANT]
> FindPrivateKey es un ejemplo que debe compilarse antes de su uso. Vea la sección [para compilar el proyecto FindPrivateKey](#to-build-the-findprivatekey-project) para obtener instrucciones sobre cómo compilar la herramienta FindPrivateKey.

Un administrador o cualquier usuario instala los certificados X.509 en el equipo. Sin embargo, se puede tener acceso al certificado mediante un servicio que se ejecuta en una cuenta diferente. Por ejemplo, la cuenta de servicio de red.

Puede que esta cuenta no tenga acceso al archivo de clave privada porque no instaló el certificado en un principio. La herramienta FindPrivateKey le da la ubicación del archivo de clave privada de un certificado X.509 determinado. Puede agregar o quitar permisos a este archivo cuando conoce la ubicación del archivo de clave privada de los certificados X.509 determinados.

Los ejemplos que usan certificados para la seguridad utilizan la herramienta FindPrivateKey en el archivo *setup. bat* . Una vez que se ha encontrado el archivo de clave privada, puede usar otras herramientas como *cacls. exe* para establecer los derechos de acceso adecuados en el archivo.

Al ejecutar un servicio de Windows Communication Foundation (WCF) bajo una cuenta de usuario, como un archivo ejecutable autohospedado, asegúrese de que la cuenta de usuario tiene acceso de solo lectura al archivo. Al ejecutar un servicio WCF en Internet Information Services (IIS), las cuentas predeterminadas en las que se ejecuta el servicio son el servicio de red en IIS 7 y versiones anteriores, o la identidad del grupo de aplicaciones en IIS 7,5 y versiones posteriores. Para obtener más información, vea [identidades del grupo de aplicaciones](/iis/manage/configuring-security/application-pool-identities).

## <a name="examples"></a>Ejemplos

Al tener acceso a un certificado para el que el proceso no tiene privilegios de lectura, verá un mensaje de excepción similar al ejemplo siguiente:

```output
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

Cuando esto suceda, use la herramienta FindPrivateKey para buscar el archivo de clave privada y, a continuación, establezca el derecho de acceso para el proceso en el que se está ejecutando el servicio. Por ejemplo, esto se puede hacer con la herramienta CACLS. exe como se muestra en el ejemplo siguiente:

```console
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a>Para compilar el proyecto FindPrivateKey

Para descargar el proyecto, visite los [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).

1. Abra el explorador de archivos y vaya a la carpeta *WF_WCF_Samples \wcf\setup\findprivatekey\cs* bajo la ubicación del directorio donde instaló el ejemplo.

2. Haga doble clic en el icono del archivo .sln para abrir el archivo en Visual Studio.

3. En el menú **compilar** , seleccione **recompilar solución**.

4. Al compilar la solución, se crea el archivo: FindPrivateKey.exe.

## <a name="conventionscommand-line-entries"></a>Convenciones: entradas de la línea de comandos

 "[*opción*]" representa un conjunto opcional de parámetros.

 "{*Option*}" representa un conjunto obligatorio de parámetros.

 "*Opción1* &#124; *opción2*" representa una opción entre los conjuntos de opciones.

 "\<*valor*>" representa un valor de parámetro que se va a escribir.

## <a name="usage"></a>Usage

```console
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

Donde:

| Parámetro         | Descripción                                                                       |
|-----------------|-----------------------------------------------------------------------------------|
| `<subjectName>` | Nombre del firmante del certificado.                                               |
| `<thumbprint>`  | La huella digital del certificado (puede usar la herramienta Certmgr. exe para encontrarlo) |
| `-f`            | solo nombre del archivo de salida                                                             |
| `-d`            | solo el directorio de salida                                                             |
| `-a`            | nombre de archivo absoluto de salida                                                         |

Si no se especifica ningún parámetro en el símbolo del sistema, se muestra el texto de ayuda con esta información.

## <a name="examples"></a>Ejemplos

Este ejemplo busca el nombre de archivo del certificado con un nombre de sujeto "CN = localhost", en el almacén personal del usuario actual.

```console
FindPrivateKey My CurrentUser -n "CN=localhost"
```

En este ejemplo se busca el nombre de archivo del certificado con un nombre de sujeto de "CN = localhost", en el almacén personal del usuario actual y se genera la ruta de acceso completa al directorio.

```console
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

Este ejemplo busca el nombre de archivo del certificado con una huella digital de "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", en el almacén personal del equipo local.

```console
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
