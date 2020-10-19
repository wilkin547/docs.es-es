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
# <a name="get-started-with-net"></a><span data-ttu-id="79392-103">Introducción a .NET</span><span class="sxs-lookup"><span data-stu-id="79392-103">Get started with .NET</span></span>

<span data-ttu-id="79392-104">En este artículo se enseña cómo crear y ejecutar una aplicación "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="79392-104">This article teaches you how to create and run a "Hello World!"</span></span> <span data-ttu-id="79392-105">de .NET.</span><span class="sxs-lookup"><span data-stu-id="79392-105">.NET app.</span></span>

<span data-ttu-id="79392-106">Si no está seguro de qué es .NET, comience con la [Introducción a .NET](introduction.md).</span><span class="sxs-lookup"><span data-stu-id="79392-106">If you're unsure what .NET is, start with the [.NET introduction](introduction.md).</span></span>

## <a name="create-an-application"></a><span data-ttu-id="79392-107">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="79392-107">Create an application</span></span>

<span data-ttu-id="79392-108">En primer lugar, descargue e instale el [SDK de .NET](https://dotnet.microsoft.com/download/dotnet-core) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="79392-108">First, download and install the [.NET SDK](https://dotnet.microsoft.com/download/dotnet-core) on your computer.</span></span>

<span data-ttu-id="79392-109">A continuación, abra un terminal como **PowerShell**, **Símbolo del sistema** o **bash**.</span><span class="sxs-lookup"><span data-stu-id="79392-109">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="79392-110">Escriba los comandos `dotnet` siguientes para crear y ejecutar una aplicación C#:</span><span class="sxs-lookup"><span data-stu-id="79392-110">Enter the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="79392-111">Verá la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="79392-111">You see the following output:</span></span>

```output
Hello World!
```

<span data-ttu-id="79392-112">Felicidades.</span><span class="sxs-lookup"><span data-stu-id="79392-112">Congratulations!</span></span> <span data-ttu-id="79392-113">Ha creado una sencilla aplicación .NET.</span><span class="sxs-lookup"><span data-stu-id="79392-113">You've created a simple .NET application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="79392-114">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="79392-114">Next steps</span></span>

<span data-ttu-id="79392-115">Para comenzar a desarrollar aplicaciones .NET puede seguir un [tutorial paso a paso](../standard/get-started.md), o bien ver los [vídeos de .NET 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) en YouTube.</span><span class="sxs-lookup"><span data-stu-id="79392-115">Get started developing .NET applications by following a [step-by-step tutorial](../standard/get-started.md) or by watching [.NET 101 videos](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) on YouTube.</span></span>
