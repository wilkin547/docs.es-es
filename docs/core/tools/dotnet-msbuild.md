---
title: Comando dotnet msbuild
description: El comando dotnet msbuild proporciona acceso a la línea de comandos de MSBuild.
ms.date: 02/14/2020
ms.openlocfilehash: 88e85868e2d7de564b2e4c90ce6e78bde4cb350e
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463623"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores

## <a name="name"></a>Name

`dotnet msbuild`: compila un proyecto y todas sus dependencias.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a>Description

El comando `dotnet msbuild` permite el acceso a una instancia de MSBuild completamente funcional.

El comando tiene exactamente las mismas funcionalidades que el cliente de línea de comandos de MSBuild existente solo para proyectos de estilo SDK. Las opciones son las mismas. Para obtener más información sobre las opciones disponibles, vea [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).

El comando [dotnet build](dotnet-build.md) es equivalente al comando `dotnet msbuild -restore -target:Build`. [dotnet build](dotnet-build.md) se usa con más frecuencia para compilar proyectos, pero dado que siempre ejecuta el destino de compilación, puede usar `dotnet msbuild` si no quiere compilar el proyecto. Por ejemplo, si hay un destino concreto que quiere ejecutar sin compilar el proyecto, use `dotnet msbuild` y especifique el destino.

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
  ```
