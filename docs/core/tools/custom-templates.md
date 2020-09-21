---
title: Plantillas personalizadas para dotnet new
description: Obtenga información sobre las plantillas personalizadas para cualquier tipo de proyecto o archivo de .NET.
author: adegeo
ms.date: 05/20/2020
ms.openlocfilehash: 1d2e5ffcb0b279f1686855834c2357827a4dc7d5
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538100"
---
# <a name="custom-templates-for-dotnet-new"></a>Plantillas personalizadas para dotnet new

El [SDK de .NET Core](https://dotnet.microsoft.com/download) cuenta con muchas plantillas ya instaladas y listas para su uso. El [comando `dotnet new`](dotnet-new.md) no es solo la forma de usar una plantilla, sino también cómo instalarlas y desinstalarlas. A partir de .NET Core 2.0, puede crear sus propias plantillas personalizadas para cualquier tipo de proyecto, como una aplicación, un servicio, una herramienta o una biblioteca de clases. Incluso puede crear una plantilla que genere uno o más archivos independientes, como un archivo de configuración.

Puede instalar plantillas personalizadas desde un paquete NuGet en cualquier fuente NuGet, haciendo referencia a un archivo *.nupkg* de NuGet directamente o especificando un directorio del sistema de archivos que contenga la plantilla. El motor de plantillas ofrece características que le permiten reemplazar valores, incluir y excluir archivos y ejecutar operaciones de procesamiento personalizadas cuando se usa la plantilla.

El motor de plantillas es de código abierto, y el repositorio de código en línea está en [dotnet/templating](https://github.com/dotnet/templating/) en GitHub. Puede encontrar más plantillas, incluidas las plantillas de terceros, en [Plantillas disponibles para dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) en GitHub. Para obtener información sobre cómo crear y usar plantillas personalizadas, vea [Cómo crear sus propias plantillas para dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) y la [Wiki del repositorio de GitHub dotnet/templating](https://github.com/dotnet/templating/wiki).

> [!NOTE]
> Los ejemplos de plantillas están disponibles en el repositorio de GitHub [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples). Sin embargo, aunque estos ejemplos son un buen recurso para aprender cómo funcionan las plantillas, el repositorio está archivado y no recibe mantenimiento. Los ejemplos pueden no estar actualizados y ya no funcionan.

Para seguir un tutorial y crear una plantilla, vea el tutorial [Creación de una plantilla personalizada para dotnet new](../tutorials/cli-templates-create-item-template.md).

### <a name="net-default-templates"></a>Plantillas predeterminadas .NET

Cuando instala el [SDK de .NET Core](https://dotnet.microsoft.com/download), recibe más de una docena de plantillas integradas para crear proyectos y archivos, incluidas las aplicaciones de consola, bibliotecas de clases, proyectos de prueba unitaria, aplicaciones de ASP.NET Core (incluidos los proyectos [Angular](https://angular.io/) y [React](https://facebook.github.io/react/)), y archivos de configuración. Para enumerar las plantillas integradas, ejecute el comando `dotnet new` con la opción `-l|--list`:

```dotnetcli
dotnet new --list
```

## <a name="configuration"></a>Configuración

Una plantilla consta de las siguientes partes:

- Archivos de origen y carpetas.
- Un archivo de configuración (*template.json*).

### <a name="source-files-and-folders"></a>Archivos de origen y carpetas

Los archivos de origen y las carpetas incluyen todos los archivos y carpetas que quiera que el motor de plantilla use cuando se ejecuta el comando `dotnet new <TEMPLATE>`. El motor de plantillas está diseñado para usar *proyectos ejecutables* como código fuente para generar proyectos. Esto presenta varias ventajas:

- El motor de plantillas no necesita que inserte tokens especiales en su código de origen del proyecto.
- Los archivos de código no son archivos especiales ni se modifican de ninguna manera para que funcionen con el motor de plantillas. Por lo tanto, las herramientas que usa normalmente para trabajar con los proyectos también funcionan con el contenido de la plantilla.
- Compile, ejecute y depure sus proyectos de plantilla de la forma en que lo hace para cualquiera de sus otros proyectos.
- Puede crear rápidamente una plantilla de un proyecto existente simplemente agregando un archivo de configuración *./.template.config/template.json* al proyecto.

Los archivos y las carpetas que se almacenan en la plantilla no se limitan a tipos de proyectos .NET formales. Los archivos de origen y las carpetas pueden constar de cualquier contenido que quiera crear cuando se use la plantilla, incluso si el motor de plantillas genera solo un archivo como su salida.

Los archivos que genera la plantilla se pueden modificar según la lógica y la configuración que ha proporcionado en el archivo de configuración *template.json*. El usuario puede invalidar esta configuración pasando las opciones al comando `dotnet new <TEMPLATE>`. Un ejemplo común de una lógica personalizada es proporcionar un nombre para una clase o variable en el archivo de código que se implementa mediante una plantilla.

### <a name="templatejson"></a>template.json

El archivo *template.json* se coloca en una carpeta *.template.config* en el directorio raíz de la plantilla. El archivo proporciona información de configuración al motor de plantillas. La configuración mínima necesita los miembros que se muestran en la tabla siguiente, que es suficiente para crear una plantilla funcional.

| Miembro            | Tipo          | Descripción |
| ----------------- | ------------- | ----------- |
| `$schema`         | Identificador URI           | El esquema JSON para el archivo *template.json*. Los editores que admiten los esquemas JSON habilitan las características de edición JSON cuando se especifica el esquema. Por ejemplo, [Visual Studio Code](https://code.visualstudio.com/) necesita este miembro para habilitar IntelliSense. Use un valor de `http://json.schemastore.org/template`. |
| `author`          | cadena        | El autor de la plantilla. |
| `classifications` | array(string) | Cero o más características de la plantilla que un usuario puede usar para buscar la plantilla al buscarla. Las clasificaciones también aparecen en la columna *Etiquetas* cuando aparece en una lista de plantillas que se han generado mediante el comando `dotnet new -l|--list`. |
| `identity`        | cadena        | Un nombre único para esta plantilla. |
| `name`            | cadena        | El nombre de la plantilla que los usuarios deben ver. |
| `shortName`       | cadena        | Un nombre abreviado predeterminado para seleccionar la plantilla que se aplica a entornos donde el usuario especifica el nombre de la plantilla; no se selecciona mediante una GUI. Por ejemplo, un nombre abreviado es útil al usar plantillas desde un símbolo del sistema con comandos de la CLI. |

El esquema completo del archivo *template.json* puede encontrarse en el [Almacenamiento del esquema JSON](http://json.schemastore.org/template). Para más información sobre el archivo *template.json*, consulte la [wiki de plantillas dotnet](https://github.com/dotnet/templating/wiki).

#### <a name="example"></a>Ejemplo

Por ejemplo, esta es una carpeta de plantillas que tiene dos archivos de contenido: *console.cs* y *readme.txt*. Tenga en cuenta que existe la carpeta requerida denominada *.template.config* que contiene el archivo *template.json*.

```text
└───mytemplate
    │   console.cs
    │   readme.txt
    │
    └───.template.config
            template.json
```

El archivo *template.json* tiene un aspecto parecido al siguiente:

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Travis Chau",
  "classifications": [ "Common", "Console" ],
  "identity": "AdatumCorporation.ConsoleTemplate.CSharp",
  "name": "Adatum Corporation Console Application",
  "shortName": "adatumconsole"
}
```

La carpeta *mytemplate* es un paquete de plantilla instalable. Una vez instalado el paquete, `shortName` se puede utilizar con el comando `dotnet new`. Por ejemplo, `dotnet new adatumconsole` generaría los archivos `console.cs` y `readme.txt` en la carpeta actual.

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a>Empaquetar una plantilla en un paquete NuGet (archivo nupkg)

Una plantilla personalizada se empaqueta con el comando la [dotnet pack](dotnet-pack.md) y un archivo *.csproj*. Como alternativa, se puede usar [NuGet](/nuget/tools/nuget-exe-cli-reference) con el comando [nuget pack](/nuget/tools/cli-ref-pack) junto con un archivo *.nuspec*. Pero NuGet necesita .NET Framework en Windows y [Mono](https://www.mono-project.com/) en Linux y macOS.

El archivo *.csproj* es ligeramente diferente al archivo *.csproj* de un proyecto de código tradicional. Tenga en cuenta la siguiente configuración:

01. El valor `<PackageType>` se agrega y se establece en `Template`.
01. El valor `<PackageVersion>` se agrega y establece en un [número de versión de NuGet](/nuget/reference/package-versioning).
01. El valor `<PackageId>` se agrega y se establece en un identificador único. Este identificador se usa para desinstalar el paquete de plantillas y lo usan las fuentes NuGet para registrar su paquete de plantillas.
01. Se debe establecer la configuración de metadatos genérica: `<Title>`, `<Authors>`, `<Description>` y `<PackageTags>`.
01. Debe establecerse la configuración `<TargetFramework>`, aunque no se usen los datos binarios generados por el proceso de la plantilla. En el ejemplo siguiente se establece en `netstandard2.0`.

Un paquete de plantillas, en forma de un paquete NuGet *.nupkg*, requiere que todas las plantillas se almacenan en la carpeta *content* dentro del paquete. Hay algunas opciones de configuración más para agregar a un archivo *.csproj* para asegurarse de que el paquete *.nupkg* generado se puede instalar como un paquete de plantilla:

01. El valor `<IncludeContentInPack>` se establece en `true` para incluir cualquier archivo que el proyecto establece como **content** en el paquete NuGet.
01. El valor `<IncludeBuildOutput>` se establece en `false` para excluir todos los archivos binarios generados por el compilador desde el paquete NuGet.
01. El valor `<ContentTargetFolders>` se establece en `content`. Esto garantiza que los archivos establecidos como **content** se almacenan en la carpeta *content* carpeta en el paquete NuGet. Esta carpeta del paquete NuGet la analiza el sistema de plantillas dotnet.

Una manera sencilla de excluir todos los archivos de código para que el proyecto de su plantilla no los compile es usando el elemento `<Compile Remove="**\*" />` del archivo de proyecto, dentro de un elemento `<ItemGroup>`.

Una manera sencilla de estructurar su paquete de plantillas es colocar todas las plantillas en carpetas individuales y luego cada carpeta de plantillas dentro de una carpeta *templates* que se encuentra en el mismo directorio que el archivo *.csproj* . De esta manera, puede usar un solo elemento del proyecto para incluir todos los archivos y carpetas en *templates* como **content**. Dentro de un elemento `<ItemGroup>`, cree un elemento `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />`.

Este es un archivo *.csproj* de ejemplo que sigue todas las pautas anteriores. Empaqueta la carpeta secundaria *templates* en la carpeta del paquete *content* y excluye cualquier archivo de código de la compilación.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageType>Template</PackageType>
    <PackageVersion>1.0</PackageVersion>
    <PackageId>AdatumCorporation.Utility.Templates</PackageId>
    <Title>AdatumCorporation Templates</Title>
    <Authors>Me</Authors>
    <Description>Templates to use when creating an application for Adatum Corporation.</Description>
    <PackageTags>dotnet-new;templates;contoso</PackageTags>
    <TargetFramework>netstandard2.0</TargetFramework>

    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

En el siguiente ejemplo se muestra la estructura de archivos y carpetas de usar *.csproj*  para crear un paquete de plantillas. El archivo *MyDotnetTemplates.csproj* y la carpeta *templates* se encuentran en la raíz de un directorio denominado *project_folder*. La carpeta *templates* contiene dos plantillas: *mytemplate1* y *mytemplate2*. Cada plantilla tiene archivos de contenido y una carpeta *.template.config* con un archivo de configuración *template.json*.

```text
project_folder
│   MyDotnetTemplates.csproj
│
└───templates
    ├───mytemplate1
    │   │   console.cs
    │   │   readme.txt
    │   │
    │   └───.template.config
    │           template.json
    │
    └───mytemplate2
        │   otherfile.cs
        │
        └───.template.config
                template.json
```

## <a name="installing-a-template"></a>Instalar una plantilla

Use el comando [dotnet new -i|--install](dotnet-new.md) para instalar un paquete.

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a>Para instalar una plantilla de un paquete NuGet almacenado en nuget.org

Use el identificador del paquete NuGet para instalar un paquete de plantillas.

```dotnetcli
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a>Para instalar una plantilla de un archivo nupkg local

Proporcione la ruta de acceso a un archivo de paquete NuGet *.nupkg*.

```dotnetcli
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a>Para instalar una plantilla desde un directorio de sistema de archivos

Las plantillas se pueden instalar desde una carpeta de plantillas, como la carpeta *mytemplate1* del ejemplo anterior. Especifique la ruta de acceso de la carpeta *.template.config*. La ruta de acceso al directorio de plantillas no es necesario que sea absoluto. Sin embargo, se requiere una ruta de acceso absoluta para desinstalar una plantilla que se instala desde una carpeta.

```dotnetcli
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="get-a-list-of-installed-templates"></a>Obtención de una lista de plantillas instaladas

El comando de desinstalación, sin ningún otro parámetro, enumerará todas las plantillas instaladas.

```dotnetcli
dotnet new -u
```

Ese comando devuelve algo similar a la salida siguiente:

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)
  Microsoft.DotNet.Common.ProjectTemplates.3.0
    Templates:
      Class library (classlib) C#
      Class library (classlib) F#
      Class library (classlib) VB
      Console Application (console) C#
      Console Application (console) F#
      Console Application (console) VB
...
```

El primer nivel de los elementos situados después de `Currently installed items:` son los identificadores usados en la desinstalación de una plantilla. Y en el ejemplo anterior, se enumeran `Microsoft.DotNet.Common.ItemTemplates` y `Microsoft.DotNet.Common.ProjectTemplates.3.0`. Si la plantilla se instaló mediante una ruta de acceso del sistema de archivos, este identificador será la ruta de acceso de la carpeta *.template.config*.

## <a name="uninstalling-a-template"></a>Desinstalación de una plantilla

Use el comando [dotnet new -u|--uninstall](dotnet-new.md) para desinstalar un paquete.

Si el paquete lo instaló una fuente de NuGet o un archivo *.nupkg* directamente, proporcione el identificador.

```dotnetcli
dotnet new -u <NUGET_PACKAGE_ID>
```

Si el paquete se instaló mediante la especificación de una ruta de acceso a la carpeta *.template.config*, use esa ruta de acceso **absoluta** para desinstalar el paquete. Puede ver la ruta de acceso absoluta de la plantilla en el resultado proporcionado por el comando `dotnet new -u`. Para obtener más información, consulte la sección [Obtención de una lista de plantillas instaladas](#get-a-list-of-installed-templates) anterior.

```dotnetcli
dotnet new -u <ABSOLUTE_FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a>Crear un proyecto con una plantilla personalizada

Después de que se instale una plantilla, use la plantilla ejecutando el comando `dotnet new <TEMPLATE>` como lo haría con cualquier otra plantilla preinstalada. También puede especificar [opciones](dotnet-new.md#options) en el comando `dotnet new`, incluidas las opciones específicas de plantilla que ha definido en la configuración de la plantilla. Proporcione el nombre breve de la plantilla directamente al comando:

```dotnetcli
dotnet new <TEMPLATE>
```

## <a name="see-also"></a>Vea también

- [Creación de una plantilla personalizada para dotnet new (tutorial)](../tutorials/cli-templates-create-item-template.md)
- [Wiki del repositorio de GitHub dotnet/templating](https://github.com/dotnet/templating/wiki)
- [Repositorio de GitHub dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples)
- [How to create your own templates for dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) (Cómo crear sus propias plantillas para dotnet new)
- [Esquema *template.json* en el Almacenamiento del esquema JSON](http://json.schemastore.org/template)
