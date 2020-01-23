---
title: Mage.exe (Herramienta de generación y edición de manifiestos)
ms.date: 12/06/2018
helpviewer_keywords:
- Manifest Generation and Editing tool
- Mage.exe
ms.assetid: 77dfe576-2962-407e-af13-82255df725a1
ms.openlocfilehash: 3752ac7108a9fcd55b61b32b889a717ef7c0faff
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714472"
---
# <a name="mageexe-manifest-generation-and-editing-tool"></a>Mage.exe (Herramienta de generación y edición de manifiestos)

La herramienta de generación y edición de manifiestos (*Mage.exe*) es una herramienta de línea de comandos que permite crear y editar manifiestos de aplicación y de implementación. Como herramienta de línea de comandos, *Mage.exe* se puede ejecutar desde scripts por lotes y desde otras aplicaciones basadas en Windows, incluidas las aplicaciones de ASP.NET.

También puede usar *MageUI.exe*, una aplicación gráfica, en lugar de *Mage.exe*. Para obtener más información, consulte [MageUI.exe (Herramienta de generación y edición de manifiestos, cliente gráfico)](mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).

Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use el Símbolo del sistema para desarrolladores de Visual Studio. Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).

En Visual Studio se incluyen dos versiones de *Mage.exe* y *MageUI.exe*. Para ver información sobre la versión, ejecute *MageUI.exe*, seleccione **Ayuda** y, después, seleccione **Acerca de**. En esta documentación se describe la versión 4.0.x.x de *Mage.exe* y *MageUI.exe*.

## <a name="syntax"></a>Sintaxis

```console
Mage [commands] [commandOptions]
```

## <a name="parameters"></a>Parámetros

En la tabla siguiente se muestran los comandos que admite *Mage.exe*. Para más información sobre las opciones que admiten estos comandos, vea [Opciones de los comandos New y Update](#new-and-update-command-options) y [Opciones del comando Sign](#sign-command-options).

|Comando|DESCRIPCIÓN|
|-------------|-----------------|
|**-cc, ClearApplicationCache**|Borra la memoria caché de aplicaciones descargadas de todas las aplicaciones que solo están disponibles en línea.|
|**-n, -New** *fileType [newOptions]*|Crea un nuevo archivo del tipo especificado. Los tipos válidos son:<br /><br /> -   `Deployment`: Crea un nuevo manifiesto de implementación.<br />-   `Application`: Crea un nuevo manifiesto de aplicación.<br /><br /> Si no especifica parámetros adicionales con este comando, se creará un archivo del tipo adecuado con etiquetas y valores de atributo predeterminados adecuados.<br /><br /> Use la opción **-ToFile** (consulte la tabla siguiente) para especificar el nombre de archivo y la ruta de acceso del nuevo archivo.<br /><br /> Use la opción **-FromDirectory** (consulte la tabla siguiente) para crear un manifiesto de aplicación con todos los ensamblados de una aplicación agregados a la sección \<dependency> del manifiesto.|
|**-u, -Update** *[filePath] [updateOptions]*|Realiza uno o varios cambios en un archivo de manifiesto. No tiene que especificar el tipo de archivo que va a editar. Mage.exe examinará el archivo mediante un conjunto de técnicas heurísticas para determinar si se trata de un manifiesto de implementación o de aplicación.<br /><br /> Si ya ha firmado un archivo con un certificado, **-Update** quitará el bloque de firma clave. Esto se debe a que la firma clave contiene un hash del archivo, y al modificar el archivo se invalida el hash.<br /><br /> Use la opción **-ToFile** (consulte la tabla siguiente) para especificar un nuevo nombre de archivo y una nueva ruta de acceso en lugar de sobrescribir el archivo existente.|
|**-s, -Sign** `[signOptions]`|Usa un par de claves o un certificado X509 para firmar un archivo. Las firmas se insertan como elementos XML dentro de los archivos.<br /><br /> Debe estar conectado a Internet al firmar un manifiesto que especifica un valor **-TimestampUri** .|
|**-ver, -Verify** *[manifest-filename]*|Comprueba que el manifiesto esté firmado correctamente. No se puede combinar con otros comandos. <br/><br/>**Disponible en .NET Framework 4.7 y versiones posteriores.**|
|**-h, -?, -Help** *[verbose]*|Describe todos los comandos disponibles y sus opciones. Especifique `verbose` para obtener ayuda detallada.|

## <a name="new-and-update-command-options"></a>Opciones de los comandos New y Update

En la tabla siguiente se muestran las opciones que admiten los comandos `-New` y `-Update`:

|Opciones|Valor predeterminado|Se aplica a|DESCRIPCIÓN|
|-------------|-------------------|----------------|-----------------|
|**-a, -Algorithm**|sha1RSA|Manifiestos de aplicación.<br /><br /> Manifiestos de implementación.|Especifica el algoritmo con el que se generarán los resúmenes de dependencia. El valor debe ser "sha256RSA" o "sha1RSA.<br /><br /> Úselo con la opción "-Update". Esta opción se omite cuando se usa la opción "-Sign".|
|**-appc, -AppCodeBase** `manifestReference`||Manifiestos de implementación.|Inserta una dirección URL o una referencia a la ruta de acceso del archivo en el archivo de manifiesto de aplicación. Este valor debe ser la ruta de acceso completa al manifiesto de aplicación.|
|**-appm, -AppManifest** `manifestPath`||Manifiestos de implementación.|Inserta una referencia al manifiesto de aplicación de una implementación en su manifiesto de implementación.<br /><br /> El archivo indicado en `manifestPath` debe existir; de lo contrario, *Mage.exe* emitirá un error. Si el archivo al que se hace referencia mediante `manifestPath` no es un manifiesto de aplicación, *Mage.exe* emitirá un error.|
|**-cf, -CertFile** `filePath`||Todos los tipos de archivo.|Especifica la ubicación de un certificado digital X509 para firmar un manifiesto o archivo de licencia. Esta opción se puede usar junto con la opción **-Password** si el certificado requiere una contraseña para archivos de intercambio de información personal (PFX). A partir de .NET Framework 4.7, si el archivo no contiene una clave privada, se necesita una combinación de las opciones **-CryptoProvider** y **-KeyContainer** opciones.<br/><br/>A partir de .NET Framework 4.6.2, *Mage.exe* firma manifiestos con CNG así como certificados CAPI.|
|**-ch, -CertHash** `hashSignature`||Todos los tipos de archivo.|El hash de un certificado digital guardado en el almacén de certificados personal del equipo cliente. Corresponde a la cadena de huella digital de un certificado digital que aparece en la consola de certificados de Windows.<br /><br /> `hashSignature` puede ir en mayúsculas o minúsculas y puede especificarse como cadena única, o bien, separando cada octeto de la huella digital mediante espacios y poniendo toda la huella digital entre comillas.|
|**-csp, -CryptoProvider** `provider-name`||Todos los tipos de archivo.|Especifica el proveedor de servicios criptográficos (CSP) que contiene el contenedor de claves privadas. Esta opción requiere la opción **-KeyContainer**.<br/><br/>Esta opción está disponible a partir de .NET Framework 4.7.|
|**-fd, -FromDirectory** `directoryPath`||Manifiestos de aplicación.|Rellena el manifiesto de aplicación con las descripciones de todos los ensamblados y archivos existentes en `directoryPath`, incluidos todos los subdirectorios, donde `directoryPath` es el directorio que contiene la aplicación que desea implementar. Para cada archivo del directorio, *Mage.exe* decide si se trata de un ensamblado o un archivo estático. Si es un ensamblado, agrega una etiqueta `<dependency>` y un atributo `installFrom` a la aplicación con el nombre del ensamblado, la base de código y la versión. Si es un archivo estático, agrega una etiqueta `<file>` . *Mage.exe* también usa un conjunto simple de técnicas heurísticas para detectar el archivo ejecutable principal de la aplicación, y lo marca como punto de entrada de la aplicación ClickOnce en el manifiesto.<br /><br /> *Mage.exe* nunca marca automáticamente un archivo como archivo de "datos". Esto debe hacerlo manualmente. Para obtener más información, vea [Cómo: Inclusión de un archivo de datos en una aplicación ClickOnce](/visualstudio/deployment/how-to-include-a-data-file-in-a-clickonce-application).<br /><br /> *Mage.exe* también genera un hash para cada archivo basándose en su tamaño. ClickOnce usa estos hashes para garantizar que nadie haya manipulado los archivos de implementación desde que se creó el manifiesto. Si se modifica alguno de los archivos de la implementación, puede ejecutar *Mage.exe* con el comando **-Update** y la opción **-FromDirectory**, para actualizar los hashes y las versiones del ensamblado de todos los archivos a los que se hace referencia.<br /><br /> **-FromDirectory** incluirá todos los archivos de todos los subdirectorios de `directoryPath`.<br /><br /> Si usa **-FromDirectory** con el comando **-Update**, *Mage.exe* quitará todos los archivos del manifiesto de aplicación que no existan en el directorio.|
|**-if, -IconFile**  `filePath`||Manifiestos de aplicación.|Especifica la ruta de acceso completa a un archivo de icono .ICO. Este icono aparece junto al nombre de la aplicación en el menú Inicio y en su entrada Agregar o quitar programas. Si no se especifica ningún icono, se usa el icono predeterminado.|
|**-ip, -IncludeProviderURL**  `url`|true|Manifiestos de implementación.|Indica si el manifiesto de implementación incluye el valor de ubicación de actualizaciones establecido por **-ProviderURL**.|
|**-i, -Install** `willInstall`|true|Manifiestos de implementación.|Indica si la aplicación ClickOnce debe instalarse en el equipo local o si debe ejecutarse desde la Web. Cuando se instala una aplicación, esta aparece en el menú **Inicio** de Windows. Los valores válidos son "true" o "t", y "false" o "f".<br /><br /> Si especifica la opción **-MinVersion** y un usuario tiene instalada una versión anterior a **-MinVersion** , forzará la instalación de la aplicación, independientemente del valor que pase a **-Install**.<br /><br /> Esta opción no se puede combinar con la opción **-ProviderURL** . Si intenta especificar ambas para el mismo manifiesto, provocará un error.|
|**-kc, -KeyContainer** `name`||Todos los tipos de archivo.|Especifica el contenedor de claves que contiene el nombre de la clave privada. Esta opción requiere la opción **CryptoProvider**.<br/><br/>Esta opción está disponible a partir de .NET Framework 4.7.|
|**-mv, -MinVersion**  `[version]`|La versión indicada en el manifiesto de implementación de ClickOnce tal y como especifica la marca **-Version** .|Manifiestos de implementación.|La versión mínima de esta aplicación que un usuario puede ejecutar. Esta marca hace que la versión con nombre de la aplicación sea una actualización necesaria. Si publica una versión del producto con una actualización para un cambio importante o una reparación de un error crítico de seguridad, puede usar esta marca para especificar que se debe instalar esta actualización y que el usuario no puede continuar ejecutando las versiones anteriores.<br /><br /> `version` tiene la misma semántica que el argumento de la marca **-Version** .|
|**-n, -Name** `nameString`|Implementar|Todos los tipos de archivo.|El nombre usado para identificar la aplicación. ClickOnce usará este nombre para identificar la aplicación en el menú **Inicio** (si la aplicación se ha configurado para instalarse automáticamente) y en los cuadros de diálogo Elevación de permisos. **Nota:**  Si va a actualizar un manifiesto existente y no especifica el nombre del publicador con esta opción, *Mage.exe* actualiza el manifiesto con el nombre de la organización definido en el equipo. Si desea usar otro nombre, utilice esta opción y especifique el nombre del publicador deseado.|
|**-pwd, -Password** `passwd`||Todos los tipos de archivo.|La contraseña usada para firmar un manifiesto con un certificado digital. Se debe usar junto con la opción **-CertFile** .|
|**-p, Processor** `processorValue`|Msil|Manifiestos de aplicación.<br /><br /> Manifiestos de implementación.|La arquitectura de microprocesador donde se ejecutará esta distribución. Este valor es obligatorio si va a preparar una o varias instalaciones cuyos ensamblados se han precompilado para un microprocesador concreto. Los valores válidos son `msil`, `x86`, `ia64`y `amd64`. `msil` es el Lenguaje intermedio de Microsoft, lo que significa que todos los ensamblados son independientes de la plataforma y Common Language Runtime (CLR) los compilará Just-In-Time cuando la aplicación se ejecute por primera vez.|
|**-pu,** **-ProviderURL** `url`||Manifiestos de implementación.|Especifica la dirección URL que ClickOnce examinará para buscar actualizaciones de la aplicación.|
|**-pub, -Publisher** `publisherName`||Manifiestos de aplicación.<br /><br /> Manifiestos de implementación.|Agrega el nombre del publicador al elemento de descripción del manifiesto de implementación o de aplicación. Cuando se usa en un manifiesto de aplicación, también se debe especificar **-UseManifestForTrust** con un valor "true" o "t"; de lo contrario, este parámetro producirá un error.|
|**-s, -SupportURL**  `url`||Manifiestos de aplicación.<br /><br /> Manifiestos de implementación.|Especifica el vínculo que aparece en Agregar o quitar programas para la aplicación ClickOnce.|
|**-ti, -TimestampUri** `uri`||Manifiestos de aplicación.<br /><br /> Manifiestos de implementación.|La dirección URL de un servicio de marca de tiempo digital. Las marcas de tiempo en los manifiestos evitan tener que volver a firmarlos en caso de que el certificado digital expire antes de implementar la versión siguiente de la aplicación. Para obtener más información, vea [Windows root certificate program members](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265983(v=ws.11))(Miembros del programa de certificados raíz de Windows).|
|**-t, -ToFile** `filePath`|-   Nuevo:<br />-   Implementación: deploy.application<br />-   Aplicación: application.exe.manifest<br />-   Actualización:<br />-   El archivo de entrada.|Todos los tipos de archivo.|Especifica la ruta de acceso de salida del archivo que se ha creado o modificado.<br /><br /> Si no se proporciona **-ToFile** al usar **-New**, la salida se escribirá en el directorio de trabajo actual. Si no se proporciona **-ToFile** al usar **-Update**, *Mage.exe* volverá a escribir el archivo en el archivo de entrada.|
|**-tr, -TrustLevel** `level`|Depende de la zona en la que reside la URL de la aplicación.|Manifiestos de aplicación.|El nivel de confianza que se concederá a la aplicación en los equipos cliente. Los valores son "Internet", "Intranet" y "FullTrust".|
|**-um, -UseManifestForTrust** `willUseForTrust`|False|Manifiestos de aplicación.|Especifica si se usará la firma digital del manifiesto de aplicación para tomar decisiones de confianza cuando la aplicación se ejecute en el cliente. Si se especifica "true" o "t", el manifiesto de aplicación se usará para las decisiones de confianza. Si se especifica "false" o "f", se usará la firma del manifiesto de implementación.|
|**-v, -Version** `versionNumber`|1.0.0.0|Manifiestos de aplicación.<br /><br /> Manifiestos de implementación.|La versión de la implementación. El argumento debe ser una cadena de versión válida con el formato "*N.N.N.N*", donde "*N*" es un entero de 32 bits sin signo.|
|**-wpf, -WPFBrowserApp**  `isWPFApp`|False|Manifiestos de aplicación.<br /><br /> Manifiestos de implementación.|Use esta marca solo para aplicaciones de Windows Presentation Foundation (WPF) que se hospedarán en Internet Explorer, y no para aplicaciones ejecutables independientes. Los valores válidos son "true" o "t", y "false" o "f".<br /><br /> Si se trata de un manifiesto de aplicación, inserta el atributo `hostInBrowser` en el elemento `entryPoint` de dicho manifiesto.<br /><br /> Si se trata de un manifiesto de implementación, establece el atributo `install` del elemento `deployment` en false y guarda el manifiesto con una extensión .xbap. Si se especifica este argumento junto con el argumento **-Install** se produce un error, ya que una aplicación hospedada en un explorador no puede ser una aplicación instalada sin conexión.|

## <a name="sign-command-options"></a>Opciones del comando Sign

En la siguiente tabla se muestran las opciones que admite el comando `-Sign` y que se aplican a todos los tipos de archivos.

|Opciones|DESCRIPCIÓN|
|-------------|-----------------|
|**-cf, -CertFile** `filePath`|Especifica la ubicación de un certificado digital para firmar un manifiesto. Esta opción se puede usar junto con la opción **-Password** si el certificado requiere una contraseña para archivos de intercambio de información personal (PFX). A partir de .NET Framework 4.7, si el archivo no contiene una clave privada, se necesita una combinación de las opciones **-CryptoProvider** y **-KeyContainer** opciones.<br/><br/>A partir de .NET Framework 4.6.2, *Mage.exe* firma manifiestos con CNG así como certificados CAPI.|
|**-ch, -CertHash** `hashSignature`|El hash de un certificado digital guardado en el almacén de certificados personal del equipo cliente. Corresponde a la propiedad de huella digital de un certificado digital que aparece en la consola de certificados de Windows.<br /><br /> `hashSignature` puede ir en mayúsculas o minúsculas y puede especificarse como cadena única, o bien, separando cada octeto de la huella digital mediante espacios y poniendo toda la huella digital entre comillas.|
**-csp, -CryptoProvider** `provider-name`|Especifica el proveedor de servicios criptográficos (CSP) que contiene el contenedor de claves privadas. Esta opción requiere la opción **-KeyContainer**.<br/><br/>Esta opción está disponible a partir de .NET Framework 4.7.|
|**-kc, -KeyContainer** `name`|Especifica el contenedor de claves que contiene el nombre de la clave privada. Esta opción requiere la opción **CryptoProvider**.<br/><br/>Esta opción está disponible a partir de .NET Framework 4.7.|
|**-pwd, -Password** `passwd`|La contraseña usada para firmar un manifiesto con un certificado digital. Se debe usar junto con la opción **-CertFile** .|
|**-t, -ToFile** `filePath`|Especifica la ruta de acceso de salida del archivo que se ha creado o modificado.|

## <a name="remarks"></a>Comentarios

Ninguno de los argumentos de *Mage.exe* distingue entre mayúsculas y minúsculas. Los comandos y las opciones pueden llevar como prefijo un guion (-) o una barra diagonal (/).

Todos los argumentos que se usan con el comando **-Sign** se pueden usar en cualquier momento con los comandos **-New** o **-Update** . Los siguientes comandos son equivalentes.

```console
mage -Sign c:\HelloWorldDeployment\HelloWorld.deploy -CertFile cert.pfx
mage -Update c:\HelloWorldDeployment\HelloWorld.deploy -CertFile cert.pfx
```

> [!NOTE]
> A partir de la versión 4.6.2 de .NET Framework, también se admiten los certificados de CNG.

 La tarea de firmar es la última que debe realizar, ya que un documento firmado usa un hash del archivo para comprobar que la firma es válida para el documento. Si realiza cambios en un archivo firmado, debe firmarlo de nuevo. Si firma un documento que ya estaba firmado, *Mage.exe* reemplazará la firma anterior por la nueva.

 Si usa la opción **-AppManifest** para rellenar un manifiesto de implementación, *Mage.exe* supone que el manifiesto de aplicación residirá en el mismo directorio que el manifiesto de implementación, en un subdirectorio con el mismo nombre que la versión actual de la implementación, y configura el manifiesto de implementación adecuadamente. Si el manifiesto de aplicación reside en otro lugar, use la opción **-AppCodeBase** para establecer la ubicación alternativa.

 Debe firmar los manifiestos de implementación y de aplicación antes de implementar la aplicación. Para obtener instrucciones sobre la firma de manifiestos, consulte [Trusted Application Deployment Overview](/visualstudio/deployment/trusted-application-deployment-overview).

 La opción **-TrustLevel** de los manifiestos de aplicación describe el conjunto de permisos que requiere una aplicación para ejecutarse en el equipo cliente. De manera predeterminada, a las aplicaciones se les asigna un nivel de confianza basado en la *zona* donde residen sus direcciones URL. Las aplicaciones implementadas en una red corporativa se colocan generalmente en la zona Intranet, mientras que las que se implementan en Internet se colocan en la zona Internet. Ambas zonas de seguridad imponen restricciones en el acceso de la aplicación a los recursos locales, siendo la zona Intranet ligeramente más permisiva que la zona Internet. La zona FullTrust otorga a las aplicaciones acceso completo a los recursos locales de un equipo. Si usa la opción **-TrustLevel** para colocar una aplicación en esta zona, el componente de administrador de confianza de CLR pedirá al usuario que decida si quiere otorgar este nivel de confianza mayor. Si va a implementar la aplicación en una red corporativa, puede usar la implementación de aplicaciones de confianza para aumentar el nivel de confianza de la aplicación sin preguntar al usuario.

 Los manifiestos de aplicación también admiten las secciones de confianza personalizadas. Esto facilita que la aplicación obedezca al principio de seguridad de solicitar un permiso mínimo, ya que puede configurar el manifiesto para que exija solo los permisos específicos necesarios para ejecutar la aplicación. *Mage.exe* no permite agregar directamente una sección de confianza personalizada. Puede agregar una mediante un editor de texto, un analizador XML o la herramienta gráfica *MageUI.exe*. Para obtener más información sobre cómo usar *MageUI.exe* para agregar secciones de confianza personalizadas, vea [MageUI.exe (Herramienta de generación y edición de manifiestos, cliente gráfico)](mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).

Visual Studio 2017 incluye la versión 4.6.1 de *Mage.exe*. Los manifiestos creados con esta versión de *Mage.exe* tienen como destino .NET Framework 4. Para elegir como destino versiones anteriores de .NET Framework, use una versión anterior de *Mage.exe*.

Cuando se agregan o se quitan ensamblados de un manifiesto existente, o se vuelve a firmar un manifiesto existente, *Mage.exe* no actualiza el manifiesto para destinarlo a .NET Framework 4.

En las siguientes tablas se muestran estas características y restricciones:

|Versión del manifiesto|Operación|Mage v2.0|Mage v4.0|
|----------------------|---------------|---------------|---------------|
|Manifiesto para aplicaciones que tienen como destino la versión 2.0 o 3.x de .NET Framework|Abrir|Aceptar|Aceptar|
||Cerrar|Aceptar|Aceptar|
||Guardar|Aceptar|Aceptar|
||Volver a firmar|Aceptar|Aceptar|
||Nuevo|Aceptar|No compatibles|
||Actualizar (ver abajo)|Aceptar|Aceptar|
|Manifiesto para aplicaciones que tienen como destino .NET Framework versión 4|Abrir|Aceptar|Aceptar|
||Cerrar|Aceptar|Aceptar|
||Guardar|Aceptar|Aceptar|
||Volver a firmar|Aceptar|Aceptar|
||Nuevo|No compatibles|Aceptar|
||Actualizar (ver abajo)|No compatibles|Aceptar|

|Versión del manifiesto|Detalles de la operación de actualización|Mage v2.0|Mage v4.0|
|----------------------|------------------------------|---------------|---------------|
|Manifiesto para aplicaciones que tienen como destino la versión 2.0 o 3.x de .NET Framework|Modificar un ensamblado|Aceptar|Aceptar|
||Agregar un ensamblado|Aceptar|Aceptar|
||Quitar un ensamblado|Aceptar|Aceptar|
|Manifiesto para aplicaciones que tienen como destino .NET Framework versión 4|Modificar un ensamblado|No compatibles|Aceptar|
||Agregar un ensamblado|No compatibles|Aceptar|
||Quitar un ensamblado|No compatibles|Aceptar|

 Mage.exe crea manifiestos que tienen como destino el perfil de cliente de .NET Framework 4. Las aplicaciones ClickOnce que tienen como destino el perfil de cliente de .NET Framework 4 se pueden ejecutar en el perfil de cliente de .NET Framework 4 y en la versión completa de .NET Framework 4. Si la aplicación tiene como destino la versión completa de .NET Framework 4 y no se puede ejecutar en el perfil de cliente de NET Framework 4, quite el elemento `<framework>` del cliente con un editor de texto y vuelva a firmar el manifiesto.

A continuación se muestra un ejemplo de un elemento `<framework>` de muestra que tiene como destino el perfil de cliente de .NET Framework 4:

```xml
<framework targetVersion="4.0" profile="client" supportedRuntime="4.0.20506" />
```

## <a name="examples"></a>Ejemplos

En el siguiente ejemplo se abre la interfaz de usuario para Mage (*MageUI.exe*).

```console
mage
```

En los ejemplos siguientes se crean un manifiesto de implementación y un manifiesto de aplicación predeterminados. Estos archivos se crean en el directorio de trabajo actual y reciben los nombres deploy.application y application.exe.manifest respectivamente.

```console
mage -New Deployment
mage -New Application
```

En el siguiente ejemplo se crea un manifiesto de aplicación con todos los ensamblados y archivos de recursos del directorio actual.

```console
mage -New Application -FromDirectory . -Version 1.0.0.0
```

El ejemplo siguiente es la continuación del ejemplo anterior; en él se especifican el nombre de implementación y el microprocesador de destino. También se especifica la dirección URL donde ClickOnce debe comprobar si hay actualizaciones.

```console
mage -New Application -FromDirectory . -Name "Hello, World! Application" -Version 1.0.0.0 -Processor "x86" -ProviderUrl http://internalserver/HelloWorld/
```

En el ejemplo siguiente se muestra cómo crear un par de manifiestos para implementar una aplicación WPF que se hospedará en Internet Explorer.

```console
mage -New Application -FromDirectory . -Version 1.0.0.0 -WPFBrowserApp true
mage -New Deployment -AppManifest 1.0.0.0\application.manifest -WPFBrowserApp true
```

En el siguiente ejemplo se crea un manifiesto de aplicación con todos los ensamblados y archivos de recursos del directorio actual y se firma.

```console
mage -New Application -FromDirectory . -Version 1.0.0.0 -KeyContainer keypair.snk -CryptoProvider "Microsoft Enhanced Cryptographic Provider v1.0"
```

En el siguiente ejemplo se actualiza un manifiesto de implementación con información procedente de un manifiesto de aplicación, y se establece la base de código para la ubicación del manifiesto de aplicación.

```console
mage -Update HelloWorld.deploy -AppManifest 1.0.0.0\application.manifest -AppCodeBase http://internalserver/HelloWorld.deploy
```

En el siguiente ejemplo se edita el manifiesto de implementación para forzar una actualización de la versión instalada del usuario.

```console
mage -Update c:\HelloWorldDeployment\HelloWorld.deploy -MinVersion 1.1.0.0
```

En el ejemplo siguiente se indica al manifiesto de implementación que recupere el manifiesto de aplicación de otro directorio.

```console
mage -Update HelloWorld.deploy -AppCodeBase http://anotherserver/HelloWorld/1.1.0.0/
```

En el ejemplo siguiente se firma un manifiesto de implementación existente mediante un certificado digital del directorio de trabajo actual.

```console
mage -Sign deploy.application -CertFile cert.pfx -Password <passwd>
```

En el ejemplo siguiente se firma un manifiesto de implementación existente mediante un certificado digital y una clave privada del directorio de trabajo actual.

```console
mage -Sign deploy.application -CertFile cert.pfx -KeyContainer keyfile.snk -CryptoProvider "Microsoft Enhanced Cryptographic Provider v1.0"
```

## <a name="see-also"></a>Vea también

- [Seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)
- [Tutorial: Implementación manual de una aplicación ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)
- [Introducción a la implementación de aplicaciones de confianza](/visualstudio/deployment/trusted-application-deployment-overview)
- [MageUI.exe (Herramienta de generación y edición de manifiestos, cliente gráfico)](mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
