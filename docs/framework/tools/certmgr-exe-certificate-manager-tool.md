---
title: "Certmgr.exe (Certificate Manager Tool) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "certificates, managing"
  - "CRLs"
  - "certificate trust lists"
  - "Certmgr.exe"
  - "Certificate Manager tool"
  - "CTLs"
  - "certificate revocation lists"
ms.assetid: 7e953b43-1374-4bbc-814f-53ca1b6b52bb
caps.latest.revision: 27
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 27
---
# Certmgr.exe (Certificate Manager Tool)
El administrador de certificados \(Certmgr.exe\) es una herramienta que administra certificados, listas de certificados de confianza \(CTL\) y listas de revocación de certificados \(CRL\).  
  
 El administrador de certificados se instala automáticamente con Visual Studio.  Para iniciar la herramienta, use [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
> [!NOTE]
>  El administrador de certificados \(Certmgr.exe\) es una utilidad de línea de comandos, mientras que Certificados \(Certmgr.msc\) es un complemento MMC \(Microsoft Management Console\).  Dado que Certmgr.msc se encuentra normalmente en el directorio del sistema Windows, al escribir `certmgr` en la línea de comandos, es posible que se cargue el complemento MMC Certificados, incluso si ha abierto el símbolo del sistema de Visual Studio.  Esto ocurre porque la ruta de acceso al complemento precede a la ruta de acceso al administrador de certificados en la variable de entorno PATH.  Si se produce este problema, puede ejecutar los comandos de Certmgr.exe especificando la ruta de acceso al archivo ejecutable.  
  
 Esta herramienta se instala automáticamente con Visual Studio.  Para ejecutar la herramienta, utilice el Símbolo del sistema para desarrolladores \(o el Símbolo del sistema de Visual Studio en Windows 7\).  Para obtener más información, vea [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Para obtener información general sobre los certificados X.509, vea [Trabajar con certificados](../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## Sintaxis  
  
```  
  
certmgr [/add | /del | /put] [options] [/s[/r registryLocation]] [sourceStorename] [/s[/r registryLocation]] [destinationStorename]  
```  
  
#### Parámetros  
  
|Argumento|Descripción|  
|---------------|-----------------|  
|*sourceStorename*|El almacén de certificados que contiene los certificados, las CTL o las CRL existentes que se van a agregar, eliminar, guardar o mostrar.  Puede ser un archivo de almacén o un almacén del sistema.|  
|*destinationStorename*|El archivo o el almacén de certificados de salida.|  
  
|Opción|Descripción|  
|------------|-----------------|  
|**\/add**|Agrega certificados, listas CTL y listas CRL a un almacén de certificados.|  
|**\/all**|Agrega todas las entradas cuando se usa con la opción **\/add**.  Elimina todas las entradas cuando se usa con la opción **\/delete**.  Muestra todas las entradas cuando se usa sin la opción **\/add** o **\/del**.  La opción **\/all** no se puede usar con la opción **\/put**.|  
|**\/c**|Agrega certificados cuando se usa con la opción **\/add**.  Elimina certificados cuando se usa con la opción **\/delete**.  Guarda certificados cuando se usa con la opción **\/put**.  Muestra certificados cuando se usa sin la opción **\/add**, **\/del** o **\/put**.|  
|**\/CRL**|Agrega listas CRL cuando se usa con **\/add**.  Elimina listas CRL cuando se usa con **\/del**.  Guarda listas CRL cuando se usa con **\/put**.  Muestra listas CRL cuando se usa sin la opción **\/add**, **\/del** o **\/put**.|  
|**\/CTL**|Agrega listas CTL cuando se usa con **\/add**.  Elimina listas CTL cuando se usa con **\/del**.  Guarda listas CTL cuando se usa con **\/put**.  Muestra listas CTL cuando se usa sin la opción **\/add**, **\/del** o **\/put**.|  
|**\/del**|Elimina certificados, listas CTL y listas CRL de un almacén de certificados.|  
|**\/e** *encodingType*|Especifica el tipo de codificación de los certificados.  El valor predeterminado es `X509_ASN_ENCODING`.|  
|**\/f** *dwFlags*|Especifica la marca usada para la apertura del almacén.  Se trata del parámetro *dwFlags* que se pasa a **CertOpenStore**.  El valor predeterminado es CERT\_SYSTEM\_STORE\_CURRENT\_USER.  Esta opción solo se tiene en cuenta si se usa la opción **\/y**.|  
|**\/h**\[**elp**\]|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|**\/n** *nam*|Especifica el nombre común del certificado que se va a agregar, eliminar o guardar.  Esta opción solo se puede usar con certificados; no se puede usar con listas CTL ni listas CRL.|  
|**\/put**|Guarda en un archivo un certificado X.509, una lista CTL o una lista CRL procedente de un almacén de certificados.  El archivo se guarda en formato X.509.  Puede usar la opción **\/7** con la opción **\/put** para guardar el archivo en formato PKCS \#7.  La opción **\/put** debe ir seguida de **\/c**, **\/CTL** o **\/CRL**.  La opción **\/all** no se puede usar con la opción **\/put**.|  
|**\/r** *location*|Identifica la ubicación del Registro del almacén del sistema.  Esta opción solo se tiene en cuenta si se especifica la opción **\/s**.  *location* debe ser uno de los siguientes:<br /><br /> -   `currentUser` indica que el almacén de certificados está bajo la clave HKEY\_CURRENT\_USER.  Este es el valor predeterminado.<br />-   `localMachine` indica que el almacén de certificados está bajo la clave HKEY\_LOCAL\_MACHINE.|  
|**\/s**|Indica que el almacén de certificados es un almacén del sistema.  Si no especifica esta opción, se considera que el tipo del almacén es **StoreFile**.|  
|**\/sha1** *sha1Hash*|Especifica el hash SHA1 del certificado, la lista CTL o la lista CRL que se va a agregar, eliminar o guardar.|  
|**\/v**|Especifica el modo detallado. Muestra información detallada sobre loa certificados, las listas CTL y las listas CRL.  Esta opción no se puede usar con las opciones **\/add**, **\/del** ni **\/put**.|  
|**\/y** *provider*|Especifica el nombre del proveedor de almacén.|  
|**\/7**|Guarda el almacén de destino como un objeto PKCS \#7.|  
|**\/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
## Comentarios  
 Certmgr.exe realiza las funciones básicas siguientes:  
  
-   Muestra certificados, listas CTL y listas CRL en la consola.  
  
-   Agrega certificados, listas CTL y listas CRL a un almacén de certificados.  
  
-   Elimina certificados, listas CTL y listas CRL de un almacén de certificados.  
  
-   Guarda en un archivo un certificado X.509, una lista CTL o una lista CRL procedente de un almacén de certificados.  
  
 Certmgr.exe funciona con dos tipos de almacenes de certificados: **StoreFile** y almacén del sistema.  No es necesario especificar el tipo de almacén de certificados; Certmgr.exe puede identificarlo y realizar las operaciones apropiadas.  
  
 Cuando se ejecuta Certmgr.exe sin especificar ninguna opción, se inicia el complemento certmgr.msc, que dispone de una interfaz gráfica de usuario \(GUI\) que permite realizar las tareas de administración de certificados que también están disponibles desde la línea de comandos.  La GUI proporciona un asistente para importación que copia certificados, listas CTL y listas CRL del disco en un almacén de certificados.  
  
 Para buscar los nombres de los almacenes de elementos X509Certificate para los parámetros `sourceStorename` y `destinationStorename`, compile y ejecute el código siguiente.  
  
 [!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)]
 [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]  
  
 Para obtener más información sobre los certificados, vea [Trabajar con certificados](../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## Ejemplos  
 El comando siguiente muestra un almacén del sistema predeterminado denominado `my` con salida detallada.  
  
```  
certmgr /v /s my  
```  
  
 El comando siguiente agrega todos los certificados de un archivo denominado `myFile.ext` a un archivo nuevo denominado `newFile.ext`.  
  
```  
certmgr /add /all /c myFile.ext newFile.ext  
```  
  
 El comando siguiente agrega el certificado de un archivo denominado `testcert.cer` al almacén del sistema `my`.  
  
```  
certmgr /add /c testcert.cer /s my  
```  
  
 El comando siguiente agrega el certificado de un archivo denominado `TrustedCert.cer` al almacén de certificados raíz.  
  
```  
certmgr /c /add TrustedCert.cer /s root  
```  
  
 El comando siguiente guarda un certificado con el nombre común `myCert` del almacén del sistema `my` en un archivo denominado `newCert.cer`.  
  
```  
certmgr /add /c /n myCert /s my newCert.cer  
```  
  
 El comando siguiente elimina todas las listas CTL del almacén del sistema `my` y guarda el almacén resultante en un archivo denominado `newStore.str`.  
  
```  
certmgr /del /all /ctl /s my newStore.str  
```  
  
 El comando siguiente guarda un certificado del almacén del sistema `my` en el archivo `newFile`.  Se le pedirá que especifique el número del certificado de `my` para colocarlo en `newFile`.  
  
```  
certmgr /put /c /s my newFile  
```  
  
## Vea también  
 [Tools](../../../docs/framework/tools/index.md)   
 [Makecert.exe \(Certificate Creation Tool\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md)   
 [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md)