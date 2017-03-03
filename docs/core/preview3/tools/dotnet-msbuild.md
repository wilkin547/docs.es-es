---
title: Comando dotnet-msbuild| Microsoft Docs
description: "El comando dotnet-msbuild proporciona acceso a la línea de comandos de MSBuild."
keywords: dotnet-msmsbuild, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: 06d4210e5dff97d3e96efff8ae8e84efc27fb7d2
ms.lasthandoff: 01/21/2017

---

#<a name="dotnet-msbuild"></a>dotnet-msbuild

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>Nombre 
dotnet-msbuild: compila un proyecto y todas sus dependencias.

## <a name="synopsis"></a>Sinopsis

`dotnet msbuild <msbuild_arguments>`

## <a name="description"></a>Descripción
El comando `dotnet msbuild` permite el acceso a una instancia de MSBuild completamente funcional. 

El comando tiene exactamente las mismas funcionalidades que el cliente de línea de comandos de MSBuild existente. Las opciones son las mismas. Puede usar la [referencia de línea de comandos de MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference) para familiarizarse con las opciones. 

## <a name="examples"></a>Ejemplos

Creación de un proyecto y sus dependencias:

`dotnet msbuild`

Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:

`dotnet msbuild /p:Configuration=Release`

Ejecuta el destino de publicación y publica para el RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

