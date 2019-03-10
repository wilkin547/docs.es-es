---
title: Plantillas personalizadas para dotnet new
description: Obtenga información sobre las plantillas personalizadas para cualquier tipo de proyecto o archivo de .NET.
author: guardrex
ms.date: 08/11/2017
ms.openlocfilehash: e37fb692640c25d7a91904b0802f97ebfab75851
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679065"
---
# <a name="custom-templates-for-dotnet-new"></a>Plantillas personalizadas para dotnet new

El [SDK de .NET Core](https://www.microsoft.com/net/download/core) incluye varias plantillas preinstaladas para su uso con el [comando `dotnet new`](dotnet-new.md). A partir de .NET Core 2.0, puede crear sus propias plantillas personalizadas para cualquier tipo de proyecto, como una aplicación, un servicio, una herramienta o una biblioteca de clases. Incluso puede crear una plantilla que genere uno o más archivos independientes, como un archivo de configuración.

Puede instalar plantillas personalizadas desde un paquete NuGet en cualquier fuente NuGet, haciendo referencia a un archivo *nupkg* de NuGet directamente o especificando un directorio del sistema de archivos que contiene la plantilla. El motor de plantillas ofrece características que le permiten reemplazar valores, incluir y excluir archivos y regiones de archivos, y ejecutar operaciones de procesamiento personalizadas cuando se usa la plantilla.

El motor de plantillas es de código abierto, y el repositorio de código en línea está en [dotnet/templating](https://github.com/dotnet/templating/) en GitHub. Visite el repositorio [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) para obtener ejemplos de plantillas. Puede encontrar más plantillas, incluidas las plantillas de terceros, en [Plantillas disponibles para dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) en GitHub. Para obtener información sobre cómo crear y usar plantillas personalizadas, vea [Cómo crear sus propias plantillas para dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) y la [Wiki del repositorio de GitHub dotnet/templating](https://github.com/dotnet/templating/wiki).

Para seguir un tutorial y crear una plantilla, vea el tutorial [Creación de una plantilla personalizada para dotnet new](~/docs/core/tutorials/create-custom-template.md).

## <a name="configuration"></a>Configuración

Una plantilla consta de los siguientes componentes:

- Archivos de origen y carpetas
- Un archivo de configuración (*template.json*)

### <a name="source-files-and-folders"></a>Archivos de origen y carpetas

Los archivos de origen y las carpetas incluyen todos los archivos y carpetas que quiera que el motor de plantilla use cuando se ejecuta el comando `dotnet new <TEMPLATE>`. El motor de plantillas está diseñado para usar *proyectos ejecutables* como código fuente para generar proyectos. Esto presenta varias ventajas:

- El motor de plantillas no necesita que inserte tokens especiales en su código de origen del proyecto.
- Los archivos de código no son archivos especiales ni se modifican de ninguna manera para que funcionen con el motor de plantillas. Por lo tanto, las herramientas que usa normalmente para trabajar con los proyectos también funcionan con el contenido de la plantilla.
- Compile, ejecute y depure sus proyectos de plantilla de la forma en que lo hace para cualquiera de sus otros proyectos.
- Puede crear rápidamente una plantilla de un proyecto existente simplemente agregando un archivo de configuración *template.json* al proyecto.

Los archivos y las carpetas que se almacenan en la plantilla no se limitan a tipos de proyectos .NET formales, como soluciones de .NET Core o .NET Framework. Los archivos de origen y las carpetas pueden constar de cualquier contenido que quiera crear cuando se use la plantilla, incluso si el motor de plantillas genera solo un archivo para su salida, como un archivo de configuración o un archivo de solución. Por ejemplo, puede crear una plantilla que contiene un archivo de origen *web.config* y crea un archivo *web.config* modificado para los proyectos donde se usa la plantilla. Las modificaciones en los archivos de origen se basan en la lógica y en las opciones que ha proporcionado en el archivo de configuración *template.json* junto con los valores que ha proporcionado el usuario que se han pasado como opciones al comando `dotnet new <TEMPLATE>`.

### <a name="templatejson"></a>template.json

El archivo *template.json* se coloca en una carpeta *.template.config* en el directorio raíz de la plantilla. El archivo proporciona información de configuración al motor de plantillas. La configuración mínima necesita los miembros que se muestran en la tabla siguiente, que es suficiente para crear una plantilla funcional.

| Miembro            | Tipo          | Descripción |
| ----------------- | ------------- | ----------- |
| `$schema`         | Identificador URI           | El esquema JSON para el archivo *template.json*. Los editores que admiten los esquemas JSON habilitan las características de edición JSON cuando se especifica el esquema. Por ejemplo, [Visual Studio Code](https://code.visualstudio.com/) necesita este miembro para habilitar IntelliSense. Use un valor de `http://json.schemastore.org/template`. |
| `author`          | cadena        | El autor de la plantilla. |
| `classifications` | array(string) | Cero o más características de la plantilla que un usuario puede usar para buscar la plantilla al buscarla. Las clasificaciones también aparecen en la columna *Etiquetas* cuando aparece en una lista de plantillas que se han generado mediante el comando <code>dotnet new -l&#124;--list</code>. |
| `identity`        | cadena        | Un nombre único para esta plantilla. |
| `name`            | cadena        | El nombre de la plantilla que los usuarios deben ver. |
| `shortName`       | cadena        | Una abreviatura predeterminada para seleccionar la plantilla que se aplica a entornos donde el usuario especifica el nombre de la plantilla; no se selecciona mediante una GUI. Por ejemplo, un nombre abreviado es útil al usar plantillas desde un símbolo del sistema con comandos de la CLI. |

#### <a name="example"></a>Ejemplo:

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Catalina Garcia",
  "classifications": [ "Common", "Console" ],
  "identity": "GarciaSoftware.ConsoleTemplate.CSharp",
  "name": "Garcia Software Console Application",
  "shortName": "garciaconsole"
}
```

El esquema completo del archivo *template.json* puede encontrarse en el [Almacenamiento del esquema JSON](http://json.schemastore.org/template).

## <a name="net-default-templates"></a>Plantillas predeterminadas .NET

Cuando instala el [SDK de .NET Core](https://www.microsoft.com/net/download/core), recibe más de una docena de plantillas integradas para crear proyectos y archivos, incluidas las aplicaciones de consola, bibliotecas de clases, proyectos de prueba unitaria, aplicaciones de ASP.NET Core (incluidos los proyectos [Angular](https://angular.io/) y [React](https://facebook.github.io/react/)), y archivos de configuración. Para enumerar las plantillas integradas, ejecute el comando `dotnet new` con la opción `-l|--list`:

```console
dotnet new -l
```

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a>Empaquetar una plantilla en un paquete NuGet (archivo nupkg)

Actualmente, una plantilla personalizada se empaqueta en Windows con [nuget.exe](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe) (no [dotnet pack](dotnet-pack.md)). Para el empaquetado multiplataforma, considere la posibilidad de usar [NuGetizer 3000](https://github.com/NuGet/Home/wiki/NuGetizer-3000).

El contenido de la carpeta del proyecto, junto con su archivo *.template.config/template.json*, se colocan en una carpeta denominada *content*. Junto a la carpeta *content*, agregue un [archivo *nuspec*](/nuget/create-packages/creating-a-package), que es un archivo de manifiesto XML que describe el contenido de un paquete y controla el proceso de crear el paquete NuGet. Dentro de un elemento **\<packageTypes>** en el archivo *nuspec*, incluya un elemento **\<packageType>** con un valor de atributo `name` de `Template`. Tanto la carpeta *content* como el archivo *nuspec* deben estar en el mismo directorio. En la tabla se muestran los elementos de archivo *nuspec* mínimos necesarios para generar una plantilla como un paquete NuGet.

| Elemento            | Tipo   | Descripción |
| ------------------ | ------ | ----------- |
| **\<authors>**     | cadena | Una lista separada por comas de los autores de los paquetes, que coinciden con los nombres de perfil de nuget.org. Estos se muestran en la galería de NuGet, en nuget.org, y se usan para hacer referencias cruzadas a paquetes de los mismos autores. |
| **\<description>** | cadena | Una descripción larga del paquete para su visualización en la interfaz de usuario. |
| **\<id>**          | cadena | El identificador del paquete que no distingue entre mayúsculas y minúsculas, que debe ser único en nuget.org o en la galería en la que se mantendrá el paquete. Los id. no pueden contener espacios ni caracteres no válidos para una URL y normalmente seguirán las reglas de espacios de nombres de .NET. Vea [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) (Elección de un identificador de paquete único y establecimiento del número de versión) para obtener instrucciones. |
| **\<packageType>** | cadena | Coloque este elemento dentro de un elemento **\<packageTypes>** entre los elementos **\<metadata>**. Establezca el atributo `name` del elemento **\<packageType>** en `Template`. |
| **\<version>**     | cadena | La versión del paquete, siguiendo el patrón de mayor.menor.revisión. Los números de versión pueden incluir un sufijo de versión preliminar, como se describe en el tema [Versiones preliminares](/nuget/create-packages/prerelease-packages#semantic-versioning). |

Consulte [.nuspec reference](/nuget/schema/nuspec) (Referencia de .nuspec) para ver el esquema de archivo de *nuspec* completo. Un archivo *nuspec* de ejemplo para una plantilla aparece en el tutorial [Creación de una plantilla personalizada para dotnet new](~/docs/core/tutorials/create-custom-template.md).

[Cree un paquete](/nuget/create-packages/creating-a-package#creating-the-package) mediante el comando `nuget pack <PATH_TO_NUSPEC_FILE>`.

## <a name="installing-a-template"></a>Instalar una plantilla

Instale una plantilla personalizada desde un paquete NuGet en cualquier fuente NuGet, haciendo referencia a un archivo *nupkg* directamente o especificando un directorio del sistema de archivos que contiene una configuración de plantilla. Use la opción `-i|--install` con el comando [dotnet new](dotnet-new.md).

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a>Para instalar una plantilla de un paquete NuGet almacenado en nuget.org

```console
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a>Para instalar una plantilla de un archivo nupkg local

```console
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a>Para instalar una plantilla desde un directorio de sistema de archivos

`FILE_SYSTEM_DIRECTORY` es la carpeta del proyecto que contiene el proyecto y la carpeta *.template.config*:

```console
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="uninstalling-a-template"></a>Desinstalación de una plantilla

Desinstale una plantilla personalizada haciendo referencia a un paquete NuGet por su `id` o especificando un directorio del sistema de archivos que contiene una configuración de plantilla. Use la opción de instalación `-u|--uninstall` con el comando [dotnet new](dotnet-new.md).

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a>Desinstalación de una plantilla de un paquete de NuGet almacenado en nuget.org

```console
dotnet new -u <NUGET_PACKAGE_ID>
```

### <a name="to-uninstall-a-template-from-a-local-nupkg-file"></a>Para desinstalar una plantilla de un archivo nupkg local

Para desinstalar la plantilla, no intente usar la ruta de acceso al archivo *nupkg*. Si intenta desinstalar una plantilla con `dotnet new -u <PATH_TO_NUPKG_FILE>`, se produce un error. Haga referencia al paquete por su `id`:

```console
dotnet new -u <NUGET_PACKAGE_ID>
```

### <a name="to-uninstall-a-template-from-a-file-system-directory"></a>Para desinstalar una plantilla desde un directorio de sistema de archivos

`FILE_SYSTEM_DIRECTORY` es la carpeta del proyecto que contiene el proyecto y la carpeta *.template.config*. La ruta de acceso especificada debe ser la ruta de acceso absoluta. Si intenta desinstalar una plantilla con una ruta de acceso relativa, se produce un error. Para más información, vea el artículo sobre [dotnet new](dotnet-new.md).

```console
dotnet new -u <FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a>Crear un proyecto con una plantilla personalizada

Después de que se instale una plantilla, use la plantilla ejecutando el comando `dotnet new <TEMPLATE>` como lo haría con cualquier otra plantilla preinstalada. También puede especificar [opciones](dotnet-new.md#options) en el comando `dotnet new`, incluidas las opciones específicas de plantilla que ha configurado en la configuración de plantilla. Proporcione el nombre breve de la plantilla directamente al comando:

```console
dotnet new <TEMPLATE>
```

## <a name="see-also"></a>Vea también

- [Creación de una plantilla personalizada para dotnet new (tutorial)](../tutorials/create-custom-template.md)
- [Wiki del repositorio de GitHub dotnet/templating](https://github.com/dotnet/templating/wiki)
- [Repositorio de GitHub dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples)
- [How to create your own templates for dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) (Cómo crear sus propias plantillas para dotnet new)
- [Esquema *template.json* en el Almacenamiento del esquema JSON](http://json.schemastore.org/template)
