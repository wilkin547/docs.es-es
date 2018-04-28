---
title: 'Comando dotnet msbuild: CLI de .NET Core'
description: El comando dotnet msbuild proporciona acceso a la línea de comandos de MSBuild.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 9e6f8b3063b4cd2a3a36cae8839d6f83e0466e03
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet msbuild`: compila un proyecto y todas sus dependencias.

## <a name="synopsis"></a>Sinopsis

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>Description

El comando `dotnet msbuild` permite el acceso a una instancia de MSBuild completamente funcional.

El comando tiene exactamente las mismas funcionalidades que el cliente de línea de comandos de MSBuild existente. Las opciones son las mismas. Use la [referencia de línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference) para más información sobre las opciones disponibles. 

## <a name="examples"></a>Ejemplos

Creación de un proyecto y sus dependencias:

`dotnet msbuild`

Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:

`dotnet msbuild /p:Configuration=Release`

Ejecuta el destino de publicación y publica para el RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

Visualización del proyecto completo con todos los destinos incluidos en el SDK:

`dotnet msbuild /pp`
