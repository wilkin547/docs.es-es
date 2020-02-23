---
title: Creación de un paquete de plantillas para dotnet new
description: Obtenga información sobre cómo crear un archivo csproj que compilará un paquete de plantillas para el comando dotnet new.
author: thraka
ms.date: 12/10/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 5bc926861dd6a501d7c2d24bd5f7c4116cc78b2c
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503490"
---
# <a name="tutorial-create-a-template-pack"></a>Tutorial: Creación de un paquete de plantillas

Con .NET Core, puede crear e implementar plantillas que generan proyectos, archivos e inclusos recursos. Este tutorial es el tercero de una serie que enseña a crear, instalar y desinstalar plantillas para usarlas con el comando `dotnet new`.

En esta parte de la serie, aprenderá a:

> [!div class="checklist"]
>
> * Crear un proyecto \*.csproj para compilar un paquete de plantillas
> * Configurar el archivo del proyecto para el empaquetado.
> * Instalar una plantilla a partir de un archivo de paquete de NuGet.
> * Desinstalar una plantilla por el identificador del paquete.

## <a name="prerequisites"></a>Requisitos previos

* Complete la [parte 1](cli-templates-create-item-template.md) y la [parte 2](cli-templates-create-project-template.md) de esta serie de tutoriales.

  En este tutorial se usan las dos plantillas que se crearon en las dos primeras partes de este tutorial. Puede usar otra plantilla siempre que la copie como una carpeta en la carpeta _working\templates\\_ .

* Abra un terminal y vaya a la carpeta _working\\_ .

## <a name="create-a-template-pack-project"></a>Creación de un proyecto de paquete de plantillas

Cuando se habla un paquete de plantillas, nos referimos a una o más plantillas empaquetadas en un archivo. Cuando instala o desinstala un paquete, se agregan o quitan todas las plantillas del paquete, respectivamente. Las partes anteriores de esta serie de tutoriales solo funcionan con plantillas individuales. Para compartir una plantilla no empaquetada, tiene que copiar la carpeta de plantilla y realizar la instalación mediante esa carpeta. Como un paquete de plantillas puede tener más de una plantilla y se trata de un solo archivo, compartirlo resulta sencillo.

Los paquetes de plantillas se representan con un archivo ( _.nupkg_) de paquete de NuGet. Y, al igual que lo que ocurre con cualquier paquete de NuGet, puede cargar el paquete de plantillas a una fuente NuGet. El comando `dotnet new -i` permite instalar un paquete de plantillas desde una fuente NuGet. Además, puede instalar un paquete de plantillas directamente desde un archivo _.nupkg_.

Por lo general, se usa un archivo del proyecto de C# para compilar el código y generar un archivo binario. Pero el proyecto también se puede usar para generar un paquete de plantillas. Si cambia la configuración del archivo _.csproj_, puede impedir que compile código y, en su lugar, incluir todos los recursos de las plantillas como recursos. Cuando se compila este proyecto, genera un paquete de NuGet de paquete de plantillas.

El paquete que va a crear incluirá la [plantilla de elemento](cli-templates-create-item-template.md) y la [plantilla de paquete](cli-templates-create-project-template.md) que creó anteriormente. Como agrupamos ambas plantillas en la carpeta _working\templates\\_ , podemos usar la carpeta _working_ para el archivo _.csproj_.

En el terminal, vaya a la carpeta _working_. Cree un proyecto nuevo y establezca el nombre en `templatepack` y la carpeta de salida en la carpeta actual.

```dotnetcli
dotnet new console -n templatepack -o .
```

El parámetro `-n` establece el nombre de archivo _.csproj_ en _templatepack.csproj_. El parámetro `-o` crea los archivos en el directorio actual. Verá un resultado similar a la salida siguiente.

```dotnetcli
dotnet new console -n templatepack -o .
```

```console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on .\templatepack.csproj...
  Restore completed in 52.38 ms for C:\working\templatepack.csproj.

Restore succeeded.
```

A continuación, abra el archivo _templatepack.csproj_ en su editor favorito y reemplace el contenido por el XML siguiente:

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

El valor `<PropertyGroup>` del XML anterior se divide en tres grupos. El primer grupo trata con las propiedades requeridas para un paquete de NuGet. Los tres valores `<Package` están relacionados con las propiedades del paquete de NuGet para identificar el paquete en una fuente NuGet. En concreto, el valor `<PackageId>` se usa para desinstalar el paquete de plantillas con un solo nombre en lugar de una ruta de acceso a un directorio. También se puede usar para instalar el paquete de plantillas desde una fuente NuGet. Los valores restantes, como `<Title>` y `<PackageTags>`, están relacionados con los metadatos que aparecen en la fuente NuGet. Para más información sobre la configuración de NuGet, consulte el artículo sobre [propiedades de NuGet y MSBuild](/nuget/reference/msbuild-targets).

La configuración `<TargetFramework>` se debe establecer de manera que MSBuild se ejecute correctamente al ejecutar el comando pack para compilar y empaquetar el proyecto.

Los tres últimos valores están relacionados con la configuración correcta del proyecto para incluir las plantillas en la carpeta correspondiente del paquete de NuGet cuando se crea.

`<ItemGroup>` contiene dos valores. En primer lugar, el valor `<Content>` incluye todo lo que hay en la carpeta _templates_ como contenido. También se establece para excluir cualquier carpeta _bin_ o carpeta _obj_ para evitar que se incluya cualquier código compilado (si probó y compiló las plantillas). En segundo lugar, el valor `<Compile>` excluye todos los archivos de código de la compilación, independientemente de dónde estén ubicados. Esto evita que el proyecto que se usa para crear un paquete de plantillas intente compilar el código en la jerarquía de carpetas _templates_.

## <a name="build-and-install"></a>Compilación e instalación

Guarde este archivo y, a continuación, ejecute el comando pack.

```dotnetcli
dotnet pack
```

Este comando compilará el proyecto y creará un paquete NuGet en la carpeta _working\bin\Debug_.

```dotnetcli
dotnet pack
```

```console
Microsoft (R) Build Engine version 16.2.0-preview-19278-01+d635043bd for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 123.86 ms for C:\working\templatepack.csproj.

  templatepack -> C:\working\bin\Debug\netstandard2.0\templatepack.dll
  Successfully created package 'C:\working\bin\Debug\AdatumCorporation.Utility.Templates.1.0.0.nupkg'.
```

A continuación, instale el archivo del paquete de plantillas con el comando `dotnet new -i PATH_TO_NUPKG_FILE`.

```console
C:\working> dotnet new -i C:\working\bin\Debug\AdatumCorporation.Utility.Templates.1.0.0.nupkg
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Example templates: string extensions              stringext             [C#]              Common/Code
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
```

Si cargó el paquete de NuGet en una fuente NuGet, puede usar el comando `dotnet new -i PACKAGEID`, donde `PACKAGEID` es igual que el valor `<PackageId>` del archivo _.csproj_. Este identificador de paquete es igual que el identificador del paquete de NuGet.

## <a name="uninstall-the-template-pack"></a>Desinstalación del paquete de plantillas

Independientemente de cómo instaló el paquete de plantillas, ya sea directamente con el archivo _.nupkg_ o mediante la fuente NuGet, el proceso de quitar un paquete de plantillas es el mismo. Use el `<PackageId>` de la plantilla que quiere desinstalar. Ejecute el comando `dotnet new -u` para ver una lista de las plantillas que están instaladas.

```dotnetcli
dotnet new -u
```

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      dotnet gitignore file (gitignore)
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)

... cut to save space ...

  NUnit3.DotNetNew.Template
    Templates:
      NUnit 3 Test Project (nunit) C#
      NUnit 3 Test Item (nunit-test) C#
      NUnit 3 Test Project (nunit) F#
      NUnit 3 Test Item (nunit-test) F#
      NUnit 3 Test Project (nunit) VB
      NUnit 3 Test Item (nunit-test) VB
  AdatumCorporation.Utility.Templates
    Templates:
      Example templates: async project (consoleasync) C#
      Example templates: string extensions (stringext) C#
```

Ejecute `dotnet new -u AdatumCorporation.Utility.Templates` para desinstalar la plantilla. El comando `dotnet new` generará información de ayuda sobre que debe omitir las plantillas que instaló previamente.

¡Enhorabuena! Ya instaló y desinstaló un paquete de plantillas.

## <a name="next-steps"></a>Pasos siguientes

Para más información sobre las plantillas, que en gran parte ya conoce, consulte el artículo [Plantillas personalizadas para dotnet new](../tools/custom-templates.md).

* [Wiki del repositorio de GitHub dotnet/templating](https://github.com/dotnet/templating/wiki)
* [Repositorio de GitHub dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples)
* [Esquema *template.json* en el Almacenamiento del esquema JSON](http://json.schemastore.org/template)
