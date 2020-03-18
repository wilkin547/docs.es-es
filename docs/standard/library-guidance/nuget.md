---
title: NuGet y bibliotecas de .NET
description: Procedimientos recomendados para el empaquetado con NuGet para bibliotecas de. NET.
ms.date: 01/15/2019
ms.openlocfilehash: f1e8d39fe2988f11ce7fd351a4d6bee6d322f2b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398536"
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

✔️ ES RECOMENDABLE usar un archivo de proyecto de estilo SDK para crear el paquete NuGet.

## <a name="package-dependencies"></a>Dependencias de paquetes

Las dependencias de paquetes NuGet se tratan detalladamente en el artículo [Dependences](./dependencies.md) (Dependencias).

## <a name="important-nuget-package-metadata"></a>Metadatos importantes del paquete NuGet

Un paquete NuGet admite numerosas [propiedades de metadatos](/nuget/reference/nuspec). La tabla siguiente contiene los metadatos principales que deben proporcionar todos los paquetes de NuGet.org:

| Nombre de la propiedad de MSBuild              | Nombre de nuspec              | Description  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | Identificador del paquete. Se puede reservar un prefijo del identificador si cumple los [criterios](/nuget/reference/id-prefix-reservation). |
| `PackageVersion`                   | `version`                  | Versión del paquete NuGet. Para información, vea [NuGet package version](./versioning.md#nuget-package-version) (Versión del paquete NuGet).             |
| `Title`                            | `title`                    | Título sencillo del paquete. El valor predeterminado es `PackageId`.             |
| `Description`                      | `description`              | Una descripción larga del paquete que se muestra en la interfaz de usuario.             |
| `Authors`                          | `authors`                  | Una lista separada por comas de los autores de los paquetes, que coinciden con los nombres de perfil de nuget.org.             |
| `PackageTags`                      | `tags`                     | Una lista delimitada por espacios de etiquetas y palabras clave que describen el paquete. Las etiquetas se usan al buscar paquetes.             |
| `PackageIconUrl`                   | `iconUrl`                  | Una dirección URL para una imagen que se va a usar como icono para el paquete. La dirección URL debe ser HTTPS y la imagen debe ser de 64x64 y tener un fondo transparente.             |
| `PackageProjectUrl`                | `projectUrl`               | Una dirección URL para la página principal del proyecto o el repositorio de origen.             |
| `PackageLicenseExpression`         | `license`                  | El [identificador SPDX](https://spdx.org/licenses/) de la licencia de proyecto. Solo las licencias OSI y FSF aprobadas pueden usar un identificador. Otras licencias deben usar `PackageLicenseFile`. Más información sobre los [metadatos de `license`](/nuget/reference/nuspec#license). |

> [!IMPORTANT]
> Un proyecto sin una licencia se establece en [copyright exclusivo](https://choosealicense.com/no-permission/) de forma predeterminada, lo que legalmente impide que otras personas lo usen.

✔️ ES RECOMENDABLE elegir un nombre de paquete NuGet con un prefijo que cumpla los [criterios](/nuget/reference/id-prefix-reservation) de reserva de prefijos de NuGet.

✔️ NO use una href HTTPS para el icono del paquete.

> Los sitios como NuGet.org se ejecutan con HTTPS habilitado y la representación de una imagen que no sea HTTPS creará una advertencia de contenido mixto.

✔️ USE una imagen de icono de paquete de 64 x 64 y que tenga un fondo transparente para obtener mejores resultados de visualización.

✔️ ES RECOMENDABLE configurar [SourceLink](./sourcelink.md) para agregar metadatos de control de código fuente a los ensamblados y los paquetes NuGet.

> SourceLink agrega automáticamente metadatos de `RepositoryUrl` y `RepositoryType` al paquete NuGet. SourceLink también agrega información sobre el código fuente exacto a partir del cual se creó el paquete. Por ejemplo, en un paquete creado a partir de un repositorio de Git se agregará el hash de confirmación como metadatos.

## <a name="pre-release-packages"></a>Paquetes de versión preliminar

Los paquetes NuGet con un sufijo de versión se consideran de [versión preliminar](/nuget/create-packages/prerelease-packages). De forma predeterminada, la interfaz de usuario del administrador de paquetes de NuGet muestra versiones estables a menos que un usuario opte por los paquetes de versión preliminar, lo que hace que dichos paquetes resulten ideales para las pruebas limitadas de usuario.

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> Un paquete estable no puede depender de un paquete de versión preliminar. Debe crear su propia versión preliminar de paquete o depender de una versión estable anterior.

![Dependencia del paquete NuGet de versión preliminar](./media/nuget/nuget-prerelease-package.png "Dependencia del paquete NuGet de versión preliminar")

✔️ PUBLIQUE un paquete de versión preliminar cuando pruebe, obtenga una vista previa o experimente.

✔️ PUBLIQUE un paquete estable cuando esté listo, de forma que otros paquetes estables puedan hacer referencia a él.

## <a name="symbol-packages"></a>Paquetes de símbolos

El compilador de .NET genera los archivos de símbolos (`*.pdb`) junto con los ensamblados. Los archivos de símbolos asignan las ubicaciones de ejecución al código fuente original, por lo que puede recorrer dicho código a medida que se ejecuta usando un depurador. NuGet admite la [generación de un paquete de símbolos independiente (`*.snupkg`)](/nuget/create-packages/symbol-packages-snupkg) que contiene archivos de símbolos junto con el paquete principal que contiene ensamblados .NET. La idea de los paquetes de símbolos es que están hospedados en un servidor de símbolos y solo se descargan mediante una herramienta como Visual Studio a petición.

NuGet.org hospeda su propio [repositorio del servidor de símbolos](/nuget/create-packages/symbol-packages-snupkg#nugetorg-symbol-server). Los desarrolladores pueden usar los símbolos que se publican en el servidor de símbolos de NuGet.org agregando `https://symbols.nuget.org/download/symbols` a sus [orígenes de símbolos en Visual Studio](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger).

> [!IMPORTANT]
> El servidor de símbolos de NuGet.org solo es compatible con los nuevos [archivos de símbolos portátiles](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`) creados por los proyectos de estilo SDK.
>
> Para usar el servidor de símbolos NuGet.org al depurar una biblioteca de .NET, los desarrolladores deben tener la versión 15.9 de Visual Studio 2017 o una posterior.

Una alternativa a la creación de un paquete de símbolos es insertar los archivos de símbolos en el paquete NuGet principal. El paquete NuGet principal será mayor, pero los archivos de símbolo insertados implican que los desarrolladores no tendrán que configurar el servidor de símbolos de NuGet.org. Si va a crear el paquete NuGet mediante un proyecto de estilo SDK, puede insertar archivos de símbolos estableciendo la propiedad `AllowedOutputExtensionsInPackageBuildOutputFolder`:

```xml
<Project Sdk="Microsoft.NET.Sdk">
 <PropertyGroup>
    <!-- Include symbol files (*.pdb) in the built .nupkg -->
    <AllowedOutputExtensionsInPackageBuildOutputFolder>$(AllowedOutputExtensionsInPackageBuildOutputFolder);.pdb</AllowedOutputExtensionsInPackageBuildOutputFolder>
  </PropertyGroup>
</Project>
```

La desventaja de los archivos de símbolos insertados es que aumentan el tamaño del paquete en aproximadamente un 30 % para las bibliotecas de .NET compiladas mediante proyectos de estilo SDK. Si el tamaño del paquete es un problema, debe publicar símbolos en un paquete de símbolos.

✔️ ES RECOMENDABLE publicar los símbolos como un paquete de símbolos (`*.snupkg`) en NuGet.org.

> Los paquetes de símbolos (`*.snupkg`) ofrecen a los desarrolladores una buena experiencia de depuración a petición sin incrementar el tamaño del paquete principal ni afectar al rendimiento de restauración para los que no tengan pensado depurar el paquete NuGet.
>
> La salvedad es que es posible que los usuarios tengan que localizar y configurar el servidor de símbolos de NuGet en su IDE (como una instalación única) para obtener los archivos de símbolos. Visual Studio 2019 versión 16.1 ha agregado el servidor de símbolos NuGet.org a la lista de predeterminados.

>[!div class="step-by-step"]
>[Anterior](strong-naming.md)
>[Siguiente](dependencies.md)
