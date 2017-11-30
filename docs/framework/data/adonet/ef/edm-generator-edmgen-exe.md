---
title: Generador de EDM (EdmGen.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe8297a1-1fc3-48ce-8eeb-f70f63f857aa
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: da99c43d9142ee754b2b48db45ca070d1ab7c4e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="edm-generator-edmgenexe"></a>Generador de EDM (EdmGen.exe)
EdmGen.exe es una herramienta de línea de comandos utilizada para trabajar con archivos de modelo y asignación de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Puede utilizar la herramienta EdmGen.exe para lo siguiente:  
  
-   Conectarse a un origen de datos utilizando un proveedor de datos .NET Framework específico del origen de datos y generar los archivos de asignación (.msl), modelo conceptual (.csdl) y modelo de almacenamiento (.ssdl) utilizados por [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Para obtener más información, consulte [Cómo: usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
-   Validar un modelo existente. Para obtener más información, consulte [Cómo: usar EdmGen.exe para validar los archivos de modelo y asignación](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md).  
  
-   Generar un o archivo de código de C# o Visual Basic que contenga las clases de objetos generados a partir de un archivo de modelo conceptual (.csdl). Para obtener más información, consulte [Cómo: usar EdmGen.exe para generar código de capa de objeto](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md).  
  
-   Generar un archivo de código de C# o Visual Basic que contenga las vistas generadas previamente para un modelo existente. Para obtener más información, [Cómo: Pre-Generate Views para mejorar el rendimiento de las consultas](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579).  
  
 La herramienta EdmGen.exe se instala en el directorio [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]. En muchos casos, se encuentra en C:\windows\Microsoft.NET\Framework\v4.0. Para los sistemas de 64 bits, se encuentra en C:\windows\Microsoft.NET\Framework64\v4.0. También puede tener acceso a la herramienta EdmGen.exe desde el símbolo del sistema de Visual Studio (haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Visual Studio 2010**, seleccione **Visual Studio Tools**y, a continuación, haga clic en **símbolo del sistema de Visual Studio 2010**).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
EdmGen /mode:choice [options]  
```  
  
## <a name="mode"></a>Modo  
 Cuando use la herramienta EdmGen.exe, deberá especificar uno de los modos siguientes.  
  
|Modo|Descripción|  
|----------|-----------------|  
|`/mode:ValidateArtifacts`|Valida los archivos .csdl, .ssdl y .msl, y muestra los errores o advertencias.<br /><br /> Esta opción requiere al menos uno de los argumentos `/inssdl` o `/incsdl`. Si se especifica `/inmsl`, también se requieren los argumentos `/inssdl` y `/incsdl`.|  
|`/mode:FullGeneration`|Utiliza la información de la conexión a bases de datos especificada en la opción `/connectionstring` y genera los archivos .csdl, .ssdl, .msl, de nivel de objetos y de vista.<br /><br /> Esta opción requiere un argumento `/connectionstring` y un argumento `/project` o bien argumentos `/outssdl`, `/outcsdl`, `/outmsdl`, `/outobjectlayer`, `/outviews`, `/namespace` y `/entitycontainer`.|  
|`/mode:FromSSDLGeneration`|Genera los archivos .csdl y .msl, el código fuente y las vistas a partir del archivo .ssdl especificado.<br /><br /> Esta opción requiere el argumento `/inssdl` y un argumento `/project`, o los argumentos `/outcsdl`, `/outmsl`, `/outobjectlayer`, `/outviews`, `/namespace,` y `/entitycontainer`.|  
|`/mode:EntityClassGeneration`|Crea un archivo de código fuente que contiene las clases que se generaron a partir del archivo .cdsl.<br /><br /> Esta opción requiere el argumento `/incsdl` y el argumento `/project` u `/outobjectlayer`. El argumento `/language` es opcional.|  
|`/mode:ViewGeneration`|Crea un archivo de código fuente que contiene las vistas generadas a partir de los archivos .csdl, .ssdl y .msl.<br /><br /> Esta opción requiere los argumentos `/inssdl`, `/incsdl`, `/inmsl,` y `/project` u `/outviews`. El argumento `/language` es opcional.|  
  
## <a name="options"></a>Opciones  
  
|Opción|Descripción|  
|------------|-----------------|  
|`/p[roject]:`\<cadena >|Especifica el nombre del proyecto que se usará. El nombre del proyecto se utiliza como valor predeterminado para la configuración del espacio de nombres, el nombre de los archivos de modelo y asignación, el nombre del archivo de origen del objeto y el nombre del archivo de código fuente de la generación de las vistas. El nombre del contenedor de entidades se establece en \<proyecto > contexto.|  
|`/prov[ider]:`\<cadena >|Nombre del proveedor de datos de [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] que se va a utilizar para generar el archivo del modelo de almacenamiento (.ssdl). El proveedor predeterminado es el [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>).|  
|`/c[onnectionstring]:`\<cadena de conexión >|Especifica la cadena que se utiliza para conectarse al origen de datos.|  
|`/incsdl:`\<archivo >|Especifica el archivo .csdl o un directorio donde se encuentran los archivos .csdl. Se puede especificar este argumento varias veces para poder especificar varios directorios o archivos .csdl. Especificar varios directorios puede ser útil para generar las clases (`/mode:EntityClassGeneration`) o las vistas (`/mode:ViewGeneration`) cuando el modelo conceptual se divide en varios archivos. Esto también puede ser útil si se desea validar varios modelos (`/mode:ValidateArtifacts`).|  
|`/refcsdl:`\<archivo >|Especifica el archivo .csdl adicional o los archivos que se usan para resolver las referencias en el archivo .csdl de origen. (El archivo .csdl de origen es el archivo que determina la opción `/incsdl`). El archivo `/refcsdl` contiene los tipos de los que el archivo .csdl de origen depende. Este argumento se puede especificar varias veces.|  
|`/inmsl:`\<archivo >|Especifica el archivo .msl o un directorio donde se encuentran los archivos .msl. Este argumento se puede especificar varias veces para poder especificar varios directorios o archivos .msl. Especificar varios directorios puede ser útil para generar las vistas (`/mode:ViewGeneration`) cuando el modelo conceptual se divide en varios archivos. Esto también puede ser útil si se desea validar varios modelos (`/mode:ValidateArtifacts`).|  
|`/inssdl:`\<archivo >|Especifica el archivo .ssdl o un directorio donde se encuentra. Se puede especificar este argumento varias veces para poder especificar varios directorios o archivos .ssdl. Esto puede ser útil si se desea validar varios modelos `(/mode:ValidateArtifacts)`.|  
|`/outcsdl:`\<archivo >|Especifica el nombre del archivo .csdl que se creará.|  
|`/outmsl:`\<archivo >|Especifica el nombre del archivo .msl que se creará.|  
|`/outssdl:`\<archivo >|Especifica el nombre del archivo .ssdl que se creará.|  
|`/outobjectlayer:`\<archivo >|Especifica el nombre del archivo de código fuente que contiene los objetos generados a partir del archivo .csdl.|  
|`/outviews:`\<archivo >|Especifica el nombre del archivo de código fuente que contiene las vistas que se generaron.|  
|`/language:`[VB &#124; CSharp]|Especifica el lenguaje de los archivos de código fuente generados. El lenguaje predeterminado es C#.|  
|`/namespace:`\<cadena >|Especifica el espacio de nombres del modelo que se va a utilizar. El espacio de nombres se establece en el archivo .csdl al ejecutar `/mode:FullGeneration` o `/mode:FromSSDLGeneration`. El espacio de nombres no se usa al ejecutar `/mode:EntityClassGeneration`.|  
|`/entitycontainer:`\<cadena >|Especifica el nombre que se va a aplicar al elemento `<EntityContainer>` en los archivos de modelo y asignación generados.|  
|`/pl[uralize]`|Aplica las reglas del idioma inglés para singulares y plurales a los nombres de `Entity`, `EntitySet` y `NavigationProperty` en el modelo conceptual. Esta opción realizará las siguientes acciones:<br /><br /> -Asegúrese todos `EntityType` nombres singulares.<br />-Asegúrese todos `EntitySet` nombres en plurales.<br />-Para cada `NavigationProperty` que devuelva a lo sumo una entidad, poner el nombre singular.<br />-Para cada `NavigationProperty` que devuelva más de una entidad, poner el nombre en plural.|  
|`/SupressForeignKeyProperties or /nofk`|Evita que las columnas de clave externa se expongan como propiedades escalares en tipos de entidad en el modelo conceptual.|  
|`/help` o `?`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|`/nologo`|Evita que se muestre el mensaje de copyright.|  
|`/targetversion:`\<cadena >|La versión de .NET Framework que se usará para compilar el código generado. Las versiones admitidas son 4 y 4.5. El valor predeterminado es 4.|  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)  
  
 [Cómo: usar EdmGen.exe para generar el código de capa de objeto](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)  
  
 [Cómo: usar EdmGen.exe para validar los archivos de asignación y de modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)  
  
## <a name="see-also"></a>Vea también  
 [Herramientas de Entity Data Model de ADO.NET](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md)  
 [Especificaciones CSDL, SSDL MSL](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
