---
title: Introducción a .NET
description: Creación de una aplicación "Hola mundo" de .NET
author: adegeo
ms.author: adegeo
ms.date: 09/29/2020
ms.custom: vs-dotnet
ms.openlocfilehash: f196f5cfe914fe7ecddec61d2abf618c21968bbd
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105159"
---
# <a name="get-started-with-net"></a>Introducción a .NET

En este artículo se enseña cómo crear y ejecutar una aplicación "Hola mundo" de .NET.

Si no está seguro de qué es .NET, comience con la [Introducción a .NET](introduction.md).

## <a name="create-an-application"></a>Crear una aplicación

En primer lugar, descargue e instale el [SDK de .NET](https://dotnet.microsoft.com/download/dotnet) en el equipo.

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
