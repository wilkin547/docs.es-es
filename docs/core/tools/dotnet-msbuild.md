---
title: 'Comando dotnet-msbuild: CLI de .NET Core | Microsoft Docs'
description: "El comando dotnet-msbuild proporciona acceso a la línea de comandos de MSBuild."
keywords: dotnet-msmsbuild, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 05/24/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
ms.translationtype: Human Translation
ms.sourcegitcommit: df4b2ddd322e4bd2ebaf444439107e88a983f988
ms.openlocfilehash: 2267ef0b5785959456ea443405b6708a423d00ba
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2017

---

# dotnet-msbuild
<a id="dotnet-msbuild" class="xliff"></a>

## Name
<a id="name" class="xliff"></a>

`dotnet-msbuild`: compila un proyecto y todas sus dependencias.

## Sinopsis
<a id="synopsis" class="xliff"></a>

`dotnet msbuild <msbuild_arguments> [-h]`

## Descripción
<a id="description" class="xliff"></a>

El comando `dotnet msbuild` permite el acceso a una instancia de MSBuild completamente funcional.

El comando tiene exactamente las mismas funcionalidades que el cliente de línea de comandos de MSBuild existente. Las opciones son las mismas. Use la [referencia de línea de comandos de MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference) para más información sobre las opciones disponibles. 

## Ejemplos
<a id="examples" class="xliff"></a>

Creación de un proyecto y sus dependencias:

`dotnet msbuild`

Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:

`dotnet msbuild /p:Configuration=Release`

Ejecuta el destino de publicación y publica para el RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

Visualización del proyecto completo con todos los destinos incluidos en el SDK:

`dotnet msbuild /pp`
