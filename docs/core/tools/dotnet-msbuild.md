---
title: Comando dotnet msbuild
description: El comando dotnet msbuild proporciona acceso a la línea de comandos de MSBuild.
ms.date: 02/14/2020
ms.openlocfilehash: 9739fe782e17db3955db087ca1781ad4280cd491
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803176"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet msbuild`: compila un proyecto y todas sus dependencias. Nota: Si hay varios, es posible que sea necesario especificar una solución o un archivo de proyecto.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a>Descripción

El comando `dotnet msbuild` permite el acceso a una instancia de MSBuild completamente funcional.

El comando tiene exactamente las mismas funcionalidades que el cliente de línea de comandos de MSBuild existente solo para proyectos de estilo SDK. Las opciones son las mismas. Para obtener más información sobre las opciones disponibles, vea [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).

El comando [dotnet build](dotnet-build.md) es equivalente al comando `dotnet msbuild -restore`. Si no quiere compilar el proyecto y hay un destino concreto que quiere ejecutar, use `dotnet build` o `dotnet msbuild` y especifique el destino.

## <a name="examples"></a>Ejemplos

- Creación de un proyecto y sus dependencias:

  ```dotnetcli
  dotnet msbuild
  ```

- Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- Ejecuta el destino de publicación y publica para el RID `osx.10.11-x64`:

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- Visualización del proyecto completo con todos los destinos incluidos en el SDK:

  ```dotnetcli
  dotnet msbuild -preprocess
  dotnet msbuild -preprocess:<fileName>.xml
  ```
