---
title: NuGet y bibliotecas de .NET
description: Procedimientos recomendados para el empaquetado con NuGet para bibliotecas de. NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 479d1786c232ef1f843877169954e847453681c9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185633"
---
# <a name="nuget"></a>NuGet

NuGet es un administrador de paquetes para el ecosistema de. NET y es la principal forma que tienen los desarrolladores para detectar y adquirir bibliotecas de código abierto de .NET. [NuGet.org](https://www.nuget.org/), un servicio gratuito proporcionado por Microsoft para hospedar paquetes NuGet, es el host principal para los paquetes NuGet públicos, pero usted puede publicar en los servicios de NuGet personalizados, como [MyGet](https://www.myget.org/) y [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).

![NuGet](./media/nuget/nuget-logo.png "NuGet")

## <a name="create-a-nuget-package"></a>Creación de un paquete NuGet

Un paquete NuGet (`*.nupkg`) es un archivo ZIP que contiene los ensamblados de .NET y los metadatos asociados.

Hay dos formas principales de crear un paquete NuGet. Es la forma más reciente y recomendada es crear un paquete a partir de un proyecto de estilo SDK (archivo de proyecto cuyo contenido empieza con `<Project Sdk="Microsoft.NET.Sdk">`). Los ensamblados y objetivos se agregan automáticamente al paquete y los metadatos restantes se agregan al archivo de MSBuild, como el nombre del paquete y el número de versión. La compilación con la el comando [`dotnet pack`](../../core/tools/dotnet-pack.md) genera un archivo `*.nupkg` en lugar de ensamblados.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <AssemblyName>Contoso.Api</AssemblyName>
    <PackageVersion>1.1.0</PackageVersion>
    <Authors>John Doe</Authors>
  </PropertyGroup>
</Project>
```

La forma anterior de crear un paquete NuGet es con un archivo `*.nuspec` y la herramienta de línea de comandos `nuget.exe`. Un archivo nuspec ofrece un excelente control pero debe especificar meticulosamente qué ensamblados y destinos se van a incluir en el paquete NuGet final. Es fácil cometer un error o que alguien se olvide de actualizar nuspec al realizar cambios. La ventaja de nuspec es que se puede usar para crear paquetes NuGet para marcos que aún no admiten un archivo de proyecto de estilo SDK.

**✔️ ES RECOMENDABLE** usar un archivo de proyecto de estilo SDK para crear el paquete NuGet.

**✔️ ES RECOMENDABLE** configurar SourceLink para agregar metadatos de control de código fuente a los ensamblados y los paquetes NuGet.

## <a name="package-dependencies"></a>Dependencias de paquetes

Las dependencias de paquetes NuGet se tratan detalladamente en el artículo [Dependences](./dependencies.md) (Dependencias).

## <a name="important-nuget-package-metadata"></a>Metadatos importantes del paquete NuGet

Un paquete NuGet admite numerosas [propiedades de metadatos](/nuget/reference/nuspec). La tabla siguiente contiene los metadatos principales que deben proporcionar todos los proyectos de código abierto:

| Nombre de la propiedad de MSBuild              | Nombre de nuspec              | Descripción  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | Identificador del paquete. Se puede reservar un prefijo del identificador si cumple los [criterios](/nuget/reference/id-prefix-reservation). |
| `PackageVersion`                   | `version`                  | Versión del paquete NuGet. Para información, vea [NuGet package version](./versioning.md#nuget-package-version) (Versión del paquete NuGet).             |
| `Title`                            | `title`                    | Título sencillo del paquete. El valor predeterminado es `PackageId`.             |
| `Description`                      | `description`              | Una descripción larga del paquete que se muestra en la interfaz de usuario.             |
| `Authors`                          | `authors`                  | Una lista separada por comas de los autores de los paquetes, que coinciden con los nombres de perfil de nuget.org.             |
| `PackageTags`                      | `tags`                     | Una lista delimitada por espacios de etiquetas y palabras clave que describen el paquete. Las etiquetas se usan al buscar paquetes.             |
| `PackageIconUrl`                   | `iconUrl`                  | Una dirección URL para una imagen que se va a usar como icono para el paquete. La dirección URL debe ser HTTPS y la imagen debe ser de 64x64 y tener un fondo transparente.             |
| `PackageProjectUrl`                | `projectUrl`               | Una dirección URL para la página principal del proyecto o el repositorio de origen.             |
| `PackageLicenseUrl`                | `licenseUrl`               | Una dirección URL a la licencia del proyecto. Puede ser la dirección URL al archivo `LICENSE` en el control de código fuente.             |

**✔️ ES RECOMENDABLE** elegir un nombre de paquete NuGet con un prefijo que cumpla los [criterios](/nuget/reference/id-prefix-reservation) de la reserva de prefijo de NuGet.

**✔️ ES RECOMENDABLE** usar el archivo `LICENSE` en el control de código fuente como `LicenseUrl`. Por ejemplo, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).

> [!IMPORTANT]
> Un proyecto sin una licencia se establece en [copyright exclusivo](https://choosealicense.com/no-permission/) de forma predeterminada, lo que impide que otras personas lo usen.

**✔️ DEBE** utilizar una href HTTPS en el icono de paquete.

> Los sitios como NuGet.org se ejecutan con HTTPS habilitado y la representación de una imagen que no sea HTTPS creará una advertencia de contenido mixto.

**✔️ DEBE** utilizar una imagen de icono de paquete de 64x64 y que tenga un fondo transparente para obtener mejores resultados de visualización.

## <a name="pre-release-packages"></a>Paquetes de versión preliminar

Los paquetes NuGet con un sufijo de versión se consideran de [versión preliminar](/nuget/create-packages/prerelease-packages). De forma predeterminada, la interfaz de usuario del administrador de paquetes de NuGet muestra versiones estables a menos que un usuario opte por los paquetes de versión preliminar, lo que hace que dichos paquetes resulten ideales para las pruebas limitadas de usuario.

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> Un paquete estable no puede depender de un paquete de versión preliminar. Debe crear su propia versión preliminar de paquete o depender de una versión estable anterior.

![Dependencia de paquete de versión preliminar NuGet](./media/nuget/nuget-prerelease-package.png "NuGet pre-release package dependency")

**✔️ DEBE** publicar un paquete de versión preliminar cuando pruebe, obtenga una vista previa o experimente.

**✔️ DEBE** publicar un paquete estable cuando esté listo, de forma que otros paquetes estables puedan hacer referencia a él.

## <a name="symbol-packages"></a>Paquetes de símbolos

El compilador de .NET genera los archivos de símbolos (`*.pdb`) junto con los ensamblados. Los archivos de símbolos asignan las ubicaciones de ejecución al código fuente original, por lo que puede recorrer dicho código a medida que se ejecuta usando un depurador. NuGet admite la [generación de un paquete de símbolos independiente](/nuget/create-packages/symbol-packages) que contiene archivos de símbolos junto con el paquete principal que contiene ensamblados .NET. La idea de los paquetes de símbolos es que están hospedados en un servidor de símbolos y solo se descargan mediante una herramienta como Visual Studio a petición.

Actualmente el host público principal para símbolos ([SymbolSource](http://www.symbolsource.org/)) no es compatible con los nuevos [archivos de símbolos portátiles](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`) creados por los proyectos estilo de SDK, y los paquetes de símbolos no son útiles. Hasta que haya un host recomendado para los paquetes de símbolos, los archivos de símbolos se pueden incrustar en el paquete NuGet principal. Si va a crear su paquete NuGet mediante un proyecto de estilo SDK, puede incrustar archivos de símbolos estableciendo la propiedad `AllowedOutputExtensionsInPackageBuildOutputFolder`: 

```xml
<Project Sdk="Microsoft.NET.Sdk">
 <PropertyGroup>
    <!-- Include symbol files (*.pdb) in the built .nupkg -->
    <AllowedOutputExtensionsInPackageBuildOutputFolder>$(AllowedOutputExtensionsInPackageBuildOutputFolder);.pdb</AllowedOutputExtensionsInPackageBuildOutputFolder>
  </PropertyGroup>
</Project>
```

**✔️ ES RECOMENDABLE** insertar los archivos de símbolos en el paquete NuGet principal.

**❌ EVITE** la creación de un paquete de símbolos que contenga archivos de símbolos.

>[!div class="step-by-step"]
[Anterior](./strong-naming.md)
[Siguiente](./dependencies.md)
