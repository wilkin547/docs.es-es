---
title: SignTool.exe (Herramienta de firma)
description: Aprenda sobre SignTool.exe, la Herramienta de firma. Esta herramienta de línea de comandos firma los archivos digitalmente, comprueba sus firmas y les aplica marcas de tiempo.
ms.date: 03/30/2017
helpviewer_keywords:
- Sign tool
- SignTool.exe
ms.assetid: 0c25ff6c-bff3-422e-b017-146a3ee86cb9
ms.openlocfilehash: f1254f345a8b3bb796217442cbad36d2e942b403
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517209"
---
# <a name="signtoolexe-sign-tool"></a>SignTool.exe (Herramienta de firma)
La herramienta Firmar es una herramienta de la línea de comandos que firma archivos digitalmente, comprueba firmas en archivos o archivos con marcas de tiempo.  
  
 Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7). Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
signtool [command] [options] [file_name | ...]  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Argumento|Descripción|  
|--------------|-----------------|  
|`command`|Uno de los cuatro comandos (`catdb`, `sign`, `Timestamp` o `Verify`) que especifica una operación para realizar en un archivo. Para obtener una descripción de cada comando, vea la tabla siguiente.|  
|`options`|Una opción que modifica un comando. Además de las opciones globales `/q` y `/v`, cada comando admite un conjunto único de opciones.|  
|`file_name`|Ruta de acceso a un archivo que se va a firmar.|  
  
 La herramienta Firmar admite los siguientes comandos. Cada comando se utiliza con conjuntos distintos de opciones, que se enumeran en las secciones respectivas.  
  
|Get-Help|Descripción|  
|-------------|-----------------|  
|`catdb`|Agrega un archivo de catálogo a una base de datos de catálogo o bien lo quita de esta. Las bases de datos de catálogo se utilizan para la búsqueda automática de archivos de catálogo y se identifican mediante un GUID. Para obtener una lista de las opciones admitidas por el comando `catdb`, vea [Opciones del comando catdb](signtool-exe.md#catdb).|  
|`sign`|Firma archivos digitalmente. Las signaturas digitales protegen los archivos contra la manipulación y permiten a los usuarios comprobar el firmante en función de un certificado de firma. Para obtener una lista de las opciones admitidas por el comando `sign`, vea [Opciones del comando sign](signtool-exe.md#sign).|  
|`Timestamp`|Asigna marcas de tiempo a archivos. Para obtener una lista de las opciones admitidas por el comando `TimeStamp`, vea [Opciones del comando TimeStamp](signtool-exe.md#TimeStamp).|  
|`Verify`|Comprueba la signatura digital de los archivos; para ello, determina si una autoridad de confianza ha emitido el certificado de firma, si se ha revocado y, opcionalmente, si es válido para una directiva determinada. Para obtener una lista de las opciones admitidas por el comando `Verify`, vea [Opciones del comando Verify](signtool-exe.md#Verify).|  
  
 Las opciones siguientes se aplican a todos los comandos de la herramienta Firmar.  
  
|Opción global|Descripción|  
|-------------------|-----------------|  
|**/q**|No muestra ninguna salida si el comando se ejecuta correctamente y muestra el resultado mínimo si se produce un error en el comando.|  
|**/v**|Muestra resultados detallados independientemente de si el comando se ejecuta correctamente o no y muestra mensajes de advertencia.|  
|**/debug**|Muestra información de depuración.|  
  
<a name="catdb"></a>
## <a name="catdb-command-options"></a>Opciones del comando catdb  
 En la tabla siguiente se enumeran las opciones que se pueden utilizar con el comando `catdb`.  
  
|Opción de catdb|Descripción|  
|------------------|-----------------|  
|`/d`|Especifica que se actualiza la base de datos de catálogo predeterminada. Si no se utiliza la opción `/d` ni la opción `/g`, la herramienta Firmar actualiza el componente del sistema y la base de datos del controlador.|  
|`/g` *GUID*|Especifica que se actualiza la base de datos de catálogo identificada por el identificador único global *GUID*.|  
|`/r`|Quita los catálogos especificados de la base de datos de catálogo. Si no se especifica esta opción, la herramienta Firmar agrega los catálogos especificados a la base de datos de catálogo.|  
|`/u`|Especifica que se genera un nombre único automáticamente para los archivos de catálogo agregados. Si es necesario, a los archivos de catálogo se les cambia el nombre para evitar que se produzcan conflictos de nombre con archivos de catálogo existentes. Si no se especifica esta opción, la herramienta Firmar sobrescribe cualquier catálogo existente que tenga el mismo nombre que el catálogo que se va a agregar.|  
  
<a name="sign"></a>
## <a name="sign-command-options"></a>Opciones del comando sign  
 En la tabla siguiente se enumeran las opciones que se pueden utilizar con el comando `sign`.  
  
|Opción del comando sign|Descripción|  
|-------------------------|-----------------|  
|`/a`|Selecciona automáticamente el mejor certificado de firma. La herramienta Firmar encuentra todos los certificados válidos que cumplan todas las condiciones especificadas y selecciona el que sea válido durante más tiempo. Si esta opción no está presente, la herramienta Firmar solo espera encontrar un certificado de firma válido.|  
|`/ac`  *file*|Agrega un certificado adicional desde *file* al bloque de signatura.|  
|`/as`|Anexa esta signatura. Si no hay ninguna signatura principal presente, esta signatura se convierte en la principal.|  
|`/c`  *CertTemplateName*|Especifica el nombre de plantilla de certificado (una extensión de Microsoft) para el certificado de firma.|  
|`/csp`  *CSPName*|Especifica el proveedor de servicios criptográficos (CSP) que contiene el contenedor de claves privadas.|  
|`/d`  *Desc*|Especifica una descripción del contenido firmado.|  
|`/du`  *URL*|Especifica el localizador uniforme de recursos (URL) de la descripción ampliada del contenido firmado.|  
|`/f`  *SignCertFile*|Especifica el certificado de firma en un archivo. Si el archivo está en formato de intercambio de información personal (PFX) y protegido por una contraseña, utilice la opción `/p` para especificar la contraseña. Si el archivo no contiene claves privadas, utilice las opciones `/csp` y `/kc` para especificar el CSP y el nombre de contenedor de claves privadas, respectivamente.|  
|`/fd`|Especifica el algoritmo de resumen de archivo que se va a usar para crear signaturas de archivo. El valor predeterminado es SHA1.|  
|`/i`  *IssuerName*|Especifica el nombre del emisor del certificado de firma. Este valor puede corresponder a una subcadena del nombre del emisor completo.|  
|`/kc`  *PrivKeyContainerName*|Especifica el nombre del contenedor de claves privadas.|  
|`/n`  *SubjectName*|Especifica el nombre del sujeto del certificado de firma. Este valor puede corresponder a una subcadena del nombre del sujeto completo.|  
|`/nph`|Si se admite, suprime los hash de página para los archivos ejecutables. La variable de entorno SIGNTOOL_PAGE_HASHES y la versión de wintrust.dll determinan el valor predeterminado. Esta opción se omite para los archivos sin PE.|  
|`/p`  *Password*|Especifica la contraseña que se debe utilizar al abrir un archivo PFX. (Utilice la opción `/f` para especificar un archivo PFX).|  
|`/p7` *Ruta de acceso*|Especifica que se genera un archivo PKCS (Estándares de criptografía de clave pública) #7 para cada archivo de contenido especificado. Los archivos PKCS #7 se denominan *path*\\*filename*.p7.|  
|`/p7ce` *Value*|Especifica opciones para el contenido PKCS #7 firmado. Establezca *Value* en "Embedded" para insertar el contenido firmado en el archivo PKCS #7 o en "DetachedSignedData" para mostrar la parte de datos firmados de un archivo PKCS #7 desasociado. Si no se utiliza la opción `/p7ce`, el contenido firmado se incrusta de forma predeterminada.|  
|`/p7co` *\<OID>*|Especifica el identificador de objeto (OID) que identifica el contenido PKCS #7 firmado.|  
|`/ph`|Si se admite, genera los hash de página para los archivos ejecutables.|  
|`/r`  *RootSubjectName*|Especifica el nombre del sujeto del certificado raíz al que el certificado de firma debe encadenarse. Este valor puede corresponder a una subcadena del nombre de sujeto completo del certificado raíz.|  
|`/s`  *StoreName*|Especifica el almacén que se va a abrir al buscar el certificado. Si no se especifica esta opción, se abre el almacén `My`.|  
|`/sha1`  *Hash*|Especifica el hash SHA1 del certificado de firma. El hash SHA1 se especifica normalmente cuando varios certificados cumplen los criterios especificados por los modificadores restantes.|  
|`/sm`|Especifica que se utiliza un almacén de equipo, en lugar de un almacén de usuario.|  
|`/t`  *URL*|Especifica la dirección URL del servidor con marca de tiempo. Si esta opción (o `/tr`) no está presente, el archivo firmado no tendrá marca de tiempo. Se genera una advertencia si se produce algún error relacionado con la marca de tiempo. Esta opción no se puede combinar con la opción `/tr`.|  
|`/td`  *alg*|Se utiliza con la opción `/tr` para solicitar un algoritmo de resumen utilizado por el servidor de marca de tiempo RFC 3161.|  
|`/tr`  *URL*|Especifica la dirección URL del servidor con marca de tiempo RFC 3161. Si esta opción (o `/t`) no está presente, el archivo firmado no tendrá marca de tiempo. Se genera una advertencia si se produce algún error relacionado con la marca de tiempo. Esta opción no se puede combinar con la opción `/t`.|  
|`/u`  *Usage*|Especifica el uso mejorado de clave (EKU) que debe encontrarse en el certificado de firma. El valor de uso se puede especificar mediante un identificador de objetos (OID) o una cadena. El uso predeterminado es "Firma de código" (1.3.6.1.5.5.7.3.3).|  
|`/uw`|Especifica el uso de "Comprobación de componentes del sistema de Windows" (1.3.6.1.4.1.311.10.3.6).|  
  
 Para obtener ejemplos de uso, vea [Using SignTool to Sign a File](/windows/desktop/SecCrypto/using-signtool-to-sign-a-file) (Usar SignTool para firmar un archivo).  
  
<a name="TimeStamp"></a>
## <a name="timestamp-command-options"></a>Opciones del comando TimeStamp  
 En la tabla siguiente se enumeran las opciones que se pueden utilizar con el comando `TimeStamp`.  
  
|Opción de TimeStamp|Descripción|  
|----------------------|-----------------|  
|`/p7`|Agrega marcas de tiempo a archivos PKCS #7.|  
|`/t`  *URL*|Especifica la dirección URL del servidor con marca de tiempo. El archivo al que se va a agregar la marca de tiempo se debe haber firmado previamente. Se requiere la opción `/t` o `/tr`.|  
|`/td`  *alg*|Solicita un algoritmo de resumen utilizado por el servidor de marca de tiempo RFC 3161. `/td` se utiliza con la opción `/tr`.|  
|`/tp` *index*|Agrega una marca de tiempo a la signatura en *index*.|  
|`/tr`  *URL*|Especifica la dirección URL del servidor con marca de tiempo RFC 3161. El archivo al que se va a agregar la marca de tiempo se debe haber firmado previamente. Se requiere la opción `/tr` o `/t`.|  
  
 Para obtener un ejemplo de uso, vea [Adding Time Stamps to Previously Signed Files](/windows/desktop/SecCrypto/adding-time-stamps-to-previously-signed-files) (Agregar marcas de tiempo a archivos ya firmados).  
  
<a name="Verify"></a>
## <a name="verify-command-options"></a>Opciones del comando Verify  
  
|Opción de Verify|Descripción|  
|-------------------|-----------------|  
|`/a`|Especifica que todos los métodos se puedan utilizar para comprobar el archivo. Primero, se buscan las bases de datos de catálogo para determinar si el archivo se firma en un catálogo. Si el archivo no se firma en un catálogo, la herramienta Firmar intenta comprobar la signatura incrustada del archivo. Se recomienda esta opción a la hora de comprobar si se pueden firmar o no archivos en un catálogo. Algunos ejemplos de estos archivos son los archivos o controladores de Windows.|  
|`/ad`|Busca el catálogo utilizando la base de datos de catálogo predeterminada.|  
|`/ag` *CatDBGUID*|Busca el catálogo en la base de datos de catálogos identificada por *CatDBGUID*.|  
|`/all`|Comprueba todas las signaturas de un archivo que incluye varias signaturas.|  
|`/as`|Busca el catálogo utilizando la base de datos de catálogo de componentes del sistema (controlador).|  
|`/c` *CatFile*|Especifica el archivo de catálogo por nombre.|  
|`/d`|Especifica que la herramienta Firmar debe imprimir la descripción y la dirección URL de esta.|  
|`/ds`  *Index*|Comprueba la signatura en una posición especificada.|  
|`/hash` (`SHA1`&#124;`SHA256`)|Especifica un algoritmo hash opcional que se usará al buscar un archivo en un catálogo.|  
|`/kp`|Especifica que la comprobación debe realizarse con la directiva de firma de controladores en modo kernel.|  
|`/ms`|Utiliza la semántica de comprobación múltiple. Este es el comportamiento predeterminado de una llamada [WinVerifyTrust](/windows/desktop/api/wintrust/nf-wintrust-winverifytrust) en Windows 8 y versiones posteriores.|  
|`/o` *Version*|Comprueba el archivo por versión del sistema operativo. *Version* tiene el formato siguiente: *PlatformID*:*VerMajor*.*VerMinor*.*BuildNumber*. *PlatformID* representa el valor subyacente de un miembro de enumeración <xref:System.PlatformID>. **Importante:**  Se recomienda el uso del modificador `/o`. Si no se especifica `/o`, SignTool.exe puede devolver resultados inesperados. Por ejemplo, si no incluye el modificador `/o`, los catálogos del sistema que se validan correctamente en un sistema operativo anterior pueden no validarse correctamente en un sistema operativo más reciente.|  
|`/p7`|Comprueba los archivos PKCS #7. No se usa ninguna directiva existente para la validación de PKCS #7. Se comprueba la signatura y se genera una cadena para el certificado de firma.|  
|`/pa`|Especifica que se debe usar la directiva de comprobación de Authenticode predeterminada. Si no se especifica la opción `/pa`, la herramienta Firmar utiliza la directiva de comprobación de controladores de Windows. Esta opción no se puede combinar con la opción `catdb`.|  
|`/pg` *PolicyGUID*|Especifica una directiva de comprobación por GUID. *PolicyGUID* corresponde a la propiedad ActionID de la directiva de comprobación. Esta opción no se puede combinar con la opción `catdb`.|  
|`/ph`|Especifica que la herramienta Firmar debe imprimir y comprobar los valores hash de la página.|  
|`/r` *RootSubjectName*|Especifica el nombre del sujeto del certificado raíz al que el certificado de firma debe encadenarse. Este valor puede corresponder a una subcadena del nombre del sujeto completo del certificado raíz.|  
|`/tw`|Especifica que se debe generar una advertencia si la signatura no tiene marca de tiempo.|  
  
 Para obtener ejemplos de uso, vea [Using SignTool to Verify a File Signature](/windows/desktop/SecCrypto/using-signtool-to-verify-a-file-signature) (Usar SignTool para comprobar una firma de archivo).  
  
## <a name="return-value"></a>Valor devuelto  
 La herramienta Firmar devuelve uno de los siguientes códigos de salida al finalizar.  
  
|Código de salida|Descripción|  
|---------------|-----------------|  
|0|La ejecución se realizó correctamente.|  
|1|Error en la ejecución.|  
|2|La ejecución ha finalizado con advertencias.|  
  
## <a name="examples"></a>Ejemplos  
 El comando siguiente agrega el archivo de catálogo MyCatalogFileName.cat al componente del sistema y la base de datos del controlador. La opción `/u` genera un nombre único si es necesario para impedir que se reemplace un archivo de catálogo existente denominado `MyCatalogFileName.cat`.  
  
```console  
signtool catdb /v /u MyCatalogFileName.cat  
```  
  
 El comando siguiente firma un archivo automáticamente y para ello usa el mejor certificado.  
  
```console  
signtool sign /a MyFile.exe  
```  
  
 El comando siguiente firma un archivo digitalmente con un certificado almacenado en un archivo PFX protegido por contraseña.  
  
```console  
signtool sign /f MyCert.pfx /p MyPassword MyFile.exe  
```  
  
 El comando siguiente firma digitalmente un archivo y le agrega una marca de tiempo. El certificado utilizado para firmar el archivo se almacena en un archivo PFX.  
  
```console  
signtool sign /f MyCert.pfx /t http://timestamp.digicert.com MyFile.exe  
```  
  
 El comando siguiente firma un archivo con un certificado ubicado en el almacén `My` cuyo nombre de sujeto sea `My Company Certificate`.  
  
```console  
signtool sign /n "My Company Certificate" MyFile.exe  
```  
  
 El comando siguiente firma un control ActiveX y proporciona información que Internet Explorer muestra cuando se le pide al usuario que instale el control.  
  
```console  
Signtool sign /f MyCert.pfx /d: "MyControl" /du http://www.example.com/MyControl/info.html MyControl.exe  
```  
  
 El comando siguiente agrega una marca de tiempo a un archivo que ya se ha firmado digitalmente.  
  
```console  
signtool timestamp /t http://timestamp.digicert.com MyFile.exe  
```  
  
 El comando siguiente comprueba que se ha firmado un archivo.  
  
```console  
signtool verify MyFile.exe  
```  
  
 El comando siguiente comprueba si un archivo del sistema puede estar firmado en un catálogo.  
  
```console  
signtool verify /a SystemFile.dll  
```  
  
 El comando siguiente comprueba un archivo del sistema firmado en un catálogo denominado `MyCatalog.cat`.  
  
```console  
signtool verify /c MyCatalog.cat SystemFile.dll  
```  
  
## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
