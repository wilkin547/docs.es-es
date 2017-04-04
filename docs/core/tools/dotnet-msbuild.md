---
title: 'Comando dotnet-msbuild: CLI de .NET Core | Microsoft Docs'
description: "El comando dotnet-msbuild proporciona acceso a la línea de comandos de MSBuild."
keywords: dotnet-msmsbuild, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 069909ab3890b75502602f57fc15df19bc7dd614
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-msbuild"></a>dotnet-msbuild

## <a name="name"></a>Name

`dotnet-msbuild`: compila un proyecto y todas sus dependencias.

## <a name="synopsis"></a>Sinopsis

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>Descripción

El comando `dotnet msbuild` permite el acceso a una instancia de MSBuild completamente funcional.

El comando tiene exactamente las mismas funcionalidades que el cliente de línea de comandos de MSBuild existente. Las opciones son las mismas. Use la [referencia de línea de comandos de MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference) para más información sobre las opciones disponibles. 

## <a name="examples"></a>Ejemplos

Creación de un proyecto y sus dependencias:

`dotnet msbuild`

Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:

`dotnet msbuild /p:Configuration=Release`

Ejecuta el destino de publicación y publica para el RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`
