---
title: Generador de EDM (EdmGen.exe)
ms.date: 03/30/2017
ms.assetid: fe8297a1-1fc3-48ce-8eeb-f70f63f857aa
ms.openlocfilehash: 82166782e25cb7a7ea23fe7faf7a30cb0e68d631
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854722"
---
# <a name="edm-generator-edmgenexe"></a>Generador de EDM (EdmGen.exe)

EdmGen. exe es una herramienta de línea de comandos que se usa para trabajar con Entity Framework los archivos de modelo y asignación. Puede utilizar la herramienta EdmGen.exe para lo siguiente:

- Conectarse a un origen de datos mediante un proveedor de datos de .NET Framework específico del origen de datos y generar los archivos de modelo conceptual (. CSDL), de modelo de almacenamiento (. SSDL) y de asignación (. MSL) utilizados por el Entity Framework. Para obtener más información, vea [Cómo: Use EdmGen. exe para generar los archivos](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)de asignación y de modelo.

- Validar un modelo existente. Para obtener más información, vea [Cómo: Use EdmGen. exe para validar los archivos](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)de asignación y de modelo.

- Generar un o archivo de código de C# o Visual Basic que contenga las clases de objetos generados a partir de un archivo de modelo conceptual (.csdl). Para obtener más información, consulte [Cómo Use EdmGen. exe para generar código](how-to-use-edmgen-exe-to-generate-object-layer-code.md)de nivel de objeto.

- Generar un archivo de código de C# o Visual Basic que contenga las vistas generadas previamente para un modelo existente. Para obtener más información [, cómo: Generar previamente vistas para mejorar el rendimiento](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))de las consultas.

La herramienta EdmGen. exe se instala en el directorio .NET Framework. En muchos casos, se encuentra en C:\windows\Microsoft.NET\Framework\v4.0. Para los sistemas de 64 bits, se encuentra en C:\windows\Microsoft.NET\Framework64\v4.0. También puede tener acceso a la herramienta EdmGen. exe desde el símbolo del sistema de Visual Studio (haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Visual Studio 2010**, seleccione **Visual Studio Tools**y, a continuación, haga clic en **Visual Studio 2010 Símbolo del sistema**).

## <a name="syntax"></a>Sintaxis

```
EdmGen /mode:choice [options]
```

## <a name="mode"></a>Mode

Cuando use la herramienta EdmGen.exe, deberá especificar uno de los modos siguientes.

|Mode|DESCRIPCIÓN|
|----------|-----------------|
|`/mode:ValidateArtifacts`|Valida los archivos .csdl, .ssdl y .msl, y muestra los errores o advertencias.<br /><br /> Esta opción requiere al menos uno de los argumentos `/inssdl` o `/incsdl`. Si se especifica `/inmsl`, también se requieren los argumentos `/inssdl` y `/incsdl`.|
|`/mode:FullGeneration`|Utiliza la información de la conexión a bases de datos especificada en la opción `/connectionstring` y genera los archivos .csdl, .ssdl, .msl, de nivel de objetos y de vista.<br /><br /> Esta opción requiere un argumento `/connectionstring` y un argumento `/project` o bien argumentos `/outssdl`, `/outcsdl`, `/outmsdl`, `/outobjectlayer`, `/outviews`, `/namespace` y `/entitycontainer`.|
|`/mode:FromSSDLGeneration`|Genera los archivos .csdl y .msl, el código fuente y las vistas a partir del archivo .ssdl especificado.<br /><br /> Esta opción requiere el argumento `/inssdl` y un argumento `/project`, o los argumentos `/outcsdl`, `/outmsl`, `/outobjectlayer`, `/outviews`, `/namespace,` y `/entitycontainer`.|
|`/mode:EntityClassGeneration`|Crea un archivo de código fuente que contiene las clases que se generaron a partir del archivo .cdsl.<br /><br /> Esta opción requiere el argumento `/incsdl` y el argumento `/project` u `/outobjectlayer`. El argumento `/language` es opcional.|
|`/mode:ViewGeneration`|Crea un archivo de código fuente que contiene las vistas generadas a partir de los archivos .csdl, .ssdl y .msl.<br /><br /> Esta opción requiere los argumentos `/inssdl`, `/incsdl`, `/inmsl,` y `/project` u `/outviews`. El argumento `/language` es opcional.|

## <a name="options"></a>Opciones

|Opción|DESCRIPCIÓN|
|------------|-----------------|
|`/p[roject]:`\<string>|Especifica el nombre del proyecto que se usará. El nombre del proyecto se utiliza como valor predeterminado para la configuración del espacio de nombres, el nombre de los archivos de modelo y asignación, el nombre del archivo de origen del objeto y el nombre del archivo de código fuente de la generación de las vistas. El nombre del contenedor de entidades se \<establece en proyecto > contexto.|
|`/prov[ider]:`\<string>|Nombre del proveedor de datos .NET Framework que se va a utilizar para generar el archivo del modelo de almacenamiento (.ssdl). El proveedor predeterminado es el Proveedor de datos .NET Framework para SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>).|
|`/c[onnectionstring]:`\<> de cadena de conexión|Especifica la cadena que se utiliza para conectarse al origen de datos.|
|`/incsdl:`\<file>|Especifica el archivo .csdl o un directorio donde se encuentran los archivos .csdl. Se puede especificar este argumento varias veces para poder especificar varios directorios o archivos .csdl. Especificar varios directorios puede ser útil para generar las clases (`/mode:EntityClassGeneration`) o las vistas (`/mode:ViewGeneration`) cuando el modelo conceptual se divide en varios archivos. Esto también puede ser útil si se desea validar varios modelos (`/mode:ValidateArtifacts`).|
|`/refcsdl:`\<file>|Especifica el archivo .csdl adicional o los archivos que se usan para resolver las referencias en el archivo .csdl de origen. (El archivo .csdl de origen es el archivo que determina la opción `/incsdl`). El archivo `/refcsdl` contiene los tipos de los que el archivo .csdl de origen depende. Este argumento se puede especificar varias veces.|
|`/inmsl:`\<file>|Especifica el archivo .msl o un directorio donde se encuentran los archivos .msl. Este argumento se puede especificar varias veces para poder especificar varios directorios o archivos .msl. Especificar varios directorios puede ser útil para generar las vistas (`/mode:ViewGeneration`) cuando el modelo conceptual se divide en varios archivos. Esto también puede ser útil si se desea validar varios modelos (`/mode:ValidateArtifacts`).|
|`/inssdl:`\<file>|Especifica el archivo .ssdl o un directorio donde se encuentra. Se puede especificar este argumento varias veces para poder especificar varios directorios o archivos .ssdl. Esto puede ser útil si se desea validar varios modelos `(/mode:ValidateArtifacts)`.|
|`/outcsdl:`\<file>|Especifica el nombre del archivo .csdl que se creará.|
|`/outmsl:`\<file>|Especifica el nombre del archivo .msl que se creará.|
|`/outssdl:`\<file>|Especifica el nombre del archivo .ssdl que se creará.|
|`/outobjectlayer:`\<file>|Especifica el nombre del archivo de código fuente que contiene los objetos generados a partir del archivo .csdl.|
|`/outviews:`\<file>|Especifica el nombre del archivo de código fuente que contiene las vistas que se generaron.|
|`/language:`[VB&#124;CSharp]|Especifica el lenguaje de los archivos de código fuente generados. El lenguaje predeterminado es C#.|
|`/namespace:`\<string>|Especifica el espacio de nombres del modelo que se va a utilizar. El espacio de nombres se establece en el archivo .csdl al ejecutar `/mode:FullGeneration` o `/mode:FromSSDLGeneration`. El espacio de nombres no se usa al ejecutar `/mode:EntityClassGeneration`.|
|`/entitycontainer:`\<string>|Especifica el nombre que se va a aplicar al elemento `<EntityContainer>` en los archivos de modelo y asignación generados.|
|`/pl[uralize]`|Aplica las reglas del idioma inglés para singulares y plurales a los nombres de `Entity`, `EntitySet` y `NavigationProperty` en el modelo conceptual. Esta opción realizará las siguientes acciones:<br /><br /> : Convierte todos `EntityType` los nombres en singular.<br />: Convierte todos `EntitySet` los nombres en plural.<br />-Por cada `NavigationProperty` que devuelva como máximo una entidad, cree el nombre singular.<br />-Por cada `NavigationProperty` que devuelva más de una entidad, convierta el nombre en plural.|
|`/SuppressForeignKeyProperties or /nofk`|Evita que las columnas de clave externa se expongan como propiedades escalares en tipos de entidad en el modelo conceptual.|
|`/help` o `?`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|
|`/nologo`|Evita que se muestre el mensaje de copyright.|
|`/targetversion:` \<string>|La versión de .NET Framework que se usará para compilar el código generado. Las versiones admitidas son 4 y 4.5. El valor predeterminado es 4.|

## <a name="in-this-section"></a>En esta sección

[Cómo: Usar EdmGen. exe para generar los archivos de asignación y de modelo](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)

[Cómo: Usar EdmGen. exe para generar código de nivel de objeto](how-to-use-edmgen-exe-to-generate-object-layer-code.md)

[Procedimientos: Usar EdmGen. exe para validar los archivos de asignación y de modelo](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)

## <a name="see-also"></a>Vea también

- [ADO.NET Entity Data Model herramientas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Entity Data Model](../entity-data-model.md)
- [Especificaciones CSDL, SSDL MSL](./language-reference/csdl-ssdl-and-msl-specifications.md)
