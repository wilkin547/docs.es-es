---
title: Comando dotnet-msbuild | SDK de .NET Core
description: "El comando dotnet-msmsbuild proporciona acceso a la línea de comandos de MSmsbuild"
keywords: dotnet-msmsbuild, CLI, comando de la CLI, .NET Core
author: mairaw
manager: wpickett
ms.date: 10/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
translationtype: Human Translation
ms.sourcegitcommit: cde9d9577246a9025d646ce2a6d574a18512146e
ms.openlocfilehash: 51a3afdcf591b8147790d78471c6fee63ceb7f2d

---

#<a name="dotnet-msbuild"></a>dotnet-msbuild

## <a name="name"></a>Nombre 
dotnet-build: compila un proyecto y todas sus dependencias. 

## <a name="synopsis"></a>Sinopsis

`dotnet msbuild <msbuild_arguments>`

## <a name="description"></a>Descripción
El comando `dotnet msbuild` permite el acceso a una instancia de MSBuild completamente funcional. 

El comando tiene exactamente las mismas funcionalidades que el cliente de línea de comandos de MSBuild existente. Las opciones son las mismas. Puede usar la [documentación existente](https://msdn.microsoft.com/en-us/library/ms164311.aspx) para familiarizarse con la referencia de comandos. 

## <a name="examples"></a>Ejemplos

Creación de un proyecto y sus dependencias:

`dotnet msbuild`

Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:

`dotnet msbuild /p:Configuration=Release`

Ejecuta el destino de publicación y publica para el RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`



<!--HONumber=Nov16_HO3-->


