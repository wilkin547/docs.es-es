---
title: Guía de .NET Core
description: .NET Core es una implementación modular y de alto rendimiento de .NET para crear aplicaciones de Windows, Linux y Mac. Obtenga información sobre .NET Core para comenzar.
author: richlander
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: ffa58600bea1f5514b25c18aa00e6d36679f2fd9
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170282"
---
# <a name="net-core-guide"></a><span data-ttu-id="92a8b-104">Guía de .NET Core</span><span class="sxs-lookup"><span data-stu-id="92a8b-104">.NET Core Guide</span></span>

<span data-ttu-id="92a8b-105">[.NET Core](about.md) es una plataforma de desarrollo de uso general de [código abierto](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) de cuyo mantenimiento se encargan Microsoft y la comunidad .NET en [GitHub](https://github.com/dotnet/core).</span><span class="sxs-lookup"><span data-stu-id="92a8b-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="92a8b-106">Es multiplataforma, admite Windows, macOS y Linux y puede usarse para compilar aplicaciones de dispositivo, nube e IoT.</span><span class="sxs-lookup"><span data-stu-id="92a8b-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

<span data-ttu-id="92a8b-107">Consulte [Acerca de .NET Core](about.md) para más información sobre .NET Core, incluidas sus características, idiomas y marcos admitidos y principales API.</span><span class="sxs-lookup"><span data-stu-id="92a8b-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="92a8b-108">Consulte los [tutoriales de .NET Core](tutorials/index.md) para aprender a crear una aplicación .NET Core sencilla.</span><span class="sxs-lookup"><span data-stu-id="92a8b-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="92a8b-109">En unos minutos su primera aplicación estará lista y funcionando.</span><span class="sxs-lookup"><span data-stu-id="92a8b-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="92a8b-110">Si quiere probar .NET Core en su explorador, consulte el tutorial en línea [Números en C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml).</span><span class="sxs-lookup"><span data-stu-id="92a8b-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) online tutorial.</span></span>

## <a name="download-net-core-21"></a><span data-ttu-id="92a8b-111">Descarga de .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="92a8b-111">Download .NET Core 2.1</span></span>

<span data-ttu-id="92a8b-112">Descargue el [SDK de .NET Core 2.1](https://www.microsoft.com/net/download) para probar .NET Core en la máquina Windows, macOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="92a8b-112">Download the [.NET Core  2.1 SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="92a8b-113">Visite [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) si prefiere usar contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="92a8b-113">Visit [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) if you prefer to use Docker containers.</span></span>

<span data-ttu-id="92a8b-114">Si busca otra versión de .NET Core, todas las versiones de .NET Core están disponibles en la [página de descargas de .NET Core](https://www.microsoft.com/net/download/archives).</span><span class="sxs-lookup"><span data-stu-id="92a8b-114">All .NET Core versions are available at [.NET Core Downloads](https://www.microsoft.com/net/download/archives) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-21"></a><span data-ttu-id="92a8b-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="92a8b-115">.NET Core 2.1</span></span>

<span data-ttu-id="92a8b-116">La última versión es [.NET Core 2.1](whats-new/dotnet-core-2-1.md).</span><span class="sxs-lookup"><span data-stu-id="92a8b-116">The latest version is [.NET Core 2.1](whats-new/dotnet-core-2-1.md).</span></span> <span data-ttu-id="92a8b-117">Las nuevas características incluyen: herramientas globales, API de alto rendimiento (como <xref:System.Span%601?displayProperty=nameWithType>), compilación JIT en capas, mejoras de rendimiento de [compilación](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) y [tiempo de ejecución](https://blogs.msdn.microsoft.com/dotnet/2018/04/18/performance-improvements-in-net-core-2-1/) y compatibilidad con Alpine y ARM32.</span><span class="sxs-lookup"><span data-stu-id="92a8b-117">New features include: global tools, high-performance APIs (such as <xref:System.Span%601?displayProperty=nameWithType>), tiered JIT compilation, [build](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) and [runtime performance improvements](https://blogs.msdn.microsoft.com/dotnet/2018/04/18/performance-improvements-in-net-core-2-1/), and support for Alpine and ARM32.</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="92a8b-118">Creación de la primera aplicación</span><span class="sxs-lookup"><span data-stu-id="92a8b-118">Create your first application</span></span>

<span data-ttu-id="92a8b-119">Después de instalar el SDK de .NET Core, abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="92a8b-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="92a8b-120">Escriba los comandos `dotnet` siguientes para crear y ejecutar una aplicación de C#.</span><span class="sxs-lookup"><span data-stu-id="92a8b-120">Type the following `dotnet` commands to create and run a C# application.</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="92a8b-121">Debería ver los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="92a8b-121">You should see the following output:</span></span>

```console
Hello World!
```

## <a name="support"></a><span data-ttu-id="92a8b-122">Compatibilidad</span><span class="sxs-lookup"><span data-stu-id="92a8b-122">Support</span></span>

<span data-ttu-id="92a8b-123">[Microsoft admite](https://www.microsoft.com/net/support/policy) .NET Core en Windows, macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="92a8b-123">.NET Core is [supported by Microsoft](https://www.microsoft.com/net/support/policy), on Windows, macOS and Linux.</span></span> <span data-ttu-id="92a8b-124">Varias veces al año, por lo general mensualmente, se actualiza para aumentar la seguridad y la calidad.</span><span class="sxs-lookup"><span data-stu-id="92a8b-124">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="92a8b-125">Las distribuciones binarias de .NET Core se compilan y prueban en servidores mantenidos por Microsoft en Azure y reciben el mismo soporte técnico que cualquier otro producto de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92a8b-125">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="92a8b-126">[Red Hat admite .NET Core](http://redhatloves.net/) en Red Hat Enterprise Linux (RHEL).</span><span class="sxs-lookup"><span data-stu-id="92a8b-126">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="92a8b-127">Red Hat compila .NET Core desde el código fuente y permite que esté disponible en [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span><span class="sxs-lookup"><span data-stu-id="92a8b-127">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="92a8b-128">Red Hat y Microsoft colaboran para asegurarse de que .NET Core funciona bien en RHEL.</span><span class="sxs-lookup"><span data-stu-id="92a8b-128">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
