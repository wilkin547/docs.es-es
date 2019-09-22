---
title: Comando dotnet msbuild
description: El comando dotnet msbuild proporciona acceso a la línea de comandos de MSBuild.
ms.date: 12/03/2018
ms.openlocfilehash: b83f1272cdd4c5fcdb6b1e34aef7692e9acc01cd
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117708"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet msbuild`: compila un proyecto y todas sus dependencias.

## <a name="synopsis"></a>Sinopsis

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>DESCRIPCIÓN

El comando `dotnet msbuild` permite el acceso a una instancia de MSBuild completamente funcional.

El comando tiene exactamente las mismas funcionalidades que el cliente de línea de comandos de MSBuild existente solo para proyectos de tipo SDK. Las opciones son las mismas. Para obtener más información sobre las opciones disponibles, vea la [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).

El comando [dotnet build](dotnet-build.md) es equivalente al comando `dotnet msbuild -restore -target:Build`. `dotnet build` suele utilizase para compilar proyectos, pero `dotnet msbuild` le aporta mayor control. Por ejemplo, si hay un destino concreto que quiere ejecutar (sin ejecutar el destino de compilación), probablemente prefiera usar `dotnet msbuild`.

## <a name="examples"></a>Ejemplos

* Creación de un proyecto y sus dependencias:

  ```dotnetcli
  dotnet msbuild
  ```

* Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:

  ```dotnetcli
  dotnet msbuild -p:Configuration=Release
  ```

* Ejecuta el destino de publicación y publica para el RID `osx.10.11-x64`:

  ```dotnetcli
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* Visualización del proyecto completo con todos los destinos incluidos en el SDK:

  ```dotnetcli
  dotnet msbuild -pp
  ```
