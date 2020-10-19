---
title: Introducción a .NET
description: Creación de una aplicación "Hola mundo" de .NET
author: adegeo
ms.author: adegeo
ms.date: 09/29/2020
ms.custom: vs-dotnet
ms.openlocfilehash: 6ad2b96e668c52ee80b707e31a63eac2433f3c9e
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756096"
---
# <a name="get-started-with-net"></a>Introducción a .NET

En este artículo se enseña cómo crear y ejecutar una aplicación "Hola mundo" de .NET.

Si no está seguro de qué es .NET, comience con la [Introducción a .NET](introduction.md).

## <a name="create-an-application"></a>Crear una aplicación

En primer lugar, descargue e instale el [SDK de .NET](https://dotnet.microsoft.com/download/dotnet-core) en el equipo.

A continuación, abra un terminal como **PowerShell**, **Símbolo del sistema** o **bash**. Escriba los comandos `dotnet` siguientes para crear y ejecutar una aplicación C#:

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

Verá la salida siguiente:

```output
Hello World!
```

Felicidades. Ha creado una sencilla aplicación .NET.

## <a name="next-steps"></a>Pasos siguientes

Para comenzar a desarrollar aplicaciones .NET puede seguir un [tutorial paso a paso](../standard/get-started.md), o bien ver los [vídeos de .NET 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) en YouTube.
