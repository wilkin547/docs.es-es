---
title: Bibliotecas de NuGet y .NET
description: Prácticas recomendadas para el empaquetado con NuGet para bibliotecas de. NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: d0ea462a7f52dd9a6b2f14be9ed5770160bf66b1
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374508"
---
# <a name="nuget"></a>NuGet

NuGet es un administrador de paquetes para el ecosistema de. NET y es los principales desarrolladores detectarán y adquieren bibliotecas de código abierto. NET. [NuGet.org](https://www.nuget.org/), un servicio gratuito proporcionado por Microsoft para hospedar paquetes de NuGet, es el host principal para los paquetes de NuGet públicos, pero puede publicar en los servicios de NuGet personalizados como [MyGet](https://www.myget.org/) y [artefactos de Azure ](https://azure.microsoft.com/services/devops/artifacts/).

![NuGet](./media/nuget/nuget-logo.png "NuGet")

## <a name="create-a-nuget-package"></a>Crear un paquete de NuGet

Un paquete NuGet (`*.nupkg`) es un archivo zip que contiene los ensamblados de .NET y los metadatos asociados.

Hay dos formas principales para crear un paquete de NuGet. Es la forma recomendada y más reciente crear un paquete desde un proyecto de estilo SDK (cuyo contenido se inicia con el archivo de proyecto `<Project Sdk="Microsoft.NET.Sdk">`). Objetivos y los ensamblados se agregan automáticamente al paquete y restante de los metadatos se agrega al archivo de MSBuild, como el número de nombre y la versión del paquete. Compilar con la [ `dotnet pack` ](../../core/tools/dotnet-pack.md) salidas de comandos un `*.nupkg` archivo en lugar de los ensamblados.

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

Es la forma anterior de la creación de un paquete de NuGet con un `*.nuspec` archivo y el `nuget.exe` herramienta de línea de comandos. Un archivo nuspec ofrece un excelente control pero debe especificar meticulosamente qué ensamblados y destinos para incluir en el último paquete de NuGet. Es fácil cometer un error o para que alguien se olvide de actualizar el archivo nuspec al realizar cambios. La ventaja de nuspec es que puede usar crear paquetes de NuGet para marcos de trabajo que aún no admiten un archivo de proyecto de estilo SDK.

**Considere la posibilidad de ✔️** mediante un archivo de proyecto de estilo del SDK para crear el paquete de NuGet.

**Considere la posibilidad de ✔️** configurar SourceLink para agregar metadatos de control de origen a los ensamblados y paquetes de NuGet.

## <a name="package-dependencies"></a>Dependencias de paquetes

Dependencias de paquetes de NuGet se tratan detalladamente en el [dependencias](./dependencies.md) artículo.

## <a name="important-nuget-package-metadata"></a>Metadatos del paquete NuGet importantes

Un paquete NuGet es compatible con muchos [propiedades de metadatos](/nuget/reference/nuspec). En la tabla siguiente contiene los metadatos básicos que deben proporcionar todos los proyectos de código abierto:

| Nombre de la propiedad de MSBuild              | Nombre de archivo NuSpec              | Descripción  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | El identificador del paquete. Se puede reservar un prefijo del identificador de si cumple la [criterios](/nuget/reference/id-prefix-reservation). |
| `PackageVersion`                   | `version`                  | Versión del paquete de NuGet. Para obtener más información, consulte [versión del paquete NuGet](./versioning.md#nuget-package-version).             |
| `Title`                            | `title`                    | Un título fácil de usar del paquete. El valor predeterminado es el `PackageId`.             |
| `Description`                      | `description`              | Una descripción larga del paquete que se muestra en la interfaz de usuario.             |
| `Authors`                          | `authors`                  | Una lista separada por comas de los autores de paquetes que coinciden con los nombres de perfil en nuget.org.             |
| `PackageTags`                      | `tags`                     | Una lista delimitada por espacios de las etiquetas y palabras clave que describen el paquete. Las etiquetas se usan al buscar paquetes.             |
| `PackageIconUrl`                   | `iconUrl`                  | Una dirección URL para una imagen para usarla como icono para el paquete. Dirección URL debe ser HTTPS y la imagen debe ser de 64 x 64 y tienen un fondo transparente.             |
| `PackageProjectUrl`                | `projectUrl`               | Una dirección URL para el repositorio de origen o de la página principal de proyecto.             |
| `PackageLicenseUrl`                | `licenseUrl`               | Una dirección URL a la licencia de proyecto. Puede ser la dirección URL a la `LICENSE` archivo de control de código fuente.             |

**Considere la posibilidad de ✔️** elegir un nombre de paquete de NuGet con un prefijo que cumpla la reserva de prefijo de NuGet [criterios](/nuget/reference/id-prefix-reservation).

**✔️, considere la posibilidad de** utilizando el `LICENSE` archivo de control de código fuente como el `LicenseUrl`. Por ejemplo, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).

> [!IMPORTANT]
> Un proyecto sin el valor predeterminado es una licencia [copyright exclusivo](https://choosealicense.com/no-permission/), lo que sea imposible que otras personas.

**HACER ✔️** utilizar un href HTTPS en el icono de paquete.

> Ejecutan sitios como NuGet.org con habilitadas para HTTPS y mostrar una imagen que no sean HTTPS, se creará una advertencia de contenido mixto.

**HACER ✔️** usar una imagen de icono de paquete que es 64 x 64 y tiene un fondo transparente para ver mejor.

## <a name="pre-release-packages"></a>Paquetes de versión preliminar

Paquetes de NuGet con un sufijo de versión se consideran [preliminares](/nuget/create-packages/prerelease-packages). De forma predeterminada, el Administrador de paquetes NuGet de UI muestra versiones estables a menos que un usuario opta por participar en preliminares de los paquetes, por lo que los paquetes preliminares ideal para las pruebas de usuario limitada.

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> Un paquete estable no puede depender de un paquete de versión preliminar. Debe realizar su propio paquete de versión preliminar o dependen de una versión estable anterior.

![Dependencia de paquetes de versión preliminar](./media/nuget/nuget-prerelease-package.png "dependencia de paquetes de versión preliminar")

**HACER ✔️** publicar un paquete de versión preliminar para probar, obtener una vista previa o experimentar.

**HACER ✔️** publicar un paquete estable cuando su listos para otros paquetes estables pueden hacer referencia a él.

## <a name="symbol-packages"></a>Paquetes de símbolos

NuGet admite [generar un paquete de símbolos independiente](/nuget/create-packages/symbol-packages) que contiene los archivos PDB junto con el paquete principal que contiene los ensamblados de .NET de depuración. La idea de los paquetes de símbolos es que están hospedados en un servidor de símbolos y sólo se descargan mediante una herramienta como Visual Studio a petición.

Actualmente el host público principal para símbolos - [SymbolSource](http://www.symbolsource.org/) -no es compatible con los archivos PDB portátiles creados por el estilo del SDK de proyectos y paquetes de símbolos no son útiles.

**Considere la posibilidad de ✔️** incrustar los archivos PDB en el paquete NuGet principal.

**Evite ❌** creación de un paquete de símbolos que contiene los archivos PDB.

>[!div class="step-by-step"]
[Anterior](./strong-naming.md)
[Siguiente](./dependencies.md)
