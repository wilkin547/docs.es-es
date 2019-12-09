---
title: Guía de .NET Core
description: .NET Core es una implementación modular y de alto rendimiento de .NET para crear aplicaciones de Windows, Linux y Mac. Obtenga información sobre .NET Core para comenzar.
author: richlander
ms.date: 12/04/2019
ms.custom: updateeachrelease
ms.openlocfilehash: b2622dba53d64c9dcf58e852d57de117fe79eb2e
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837017"
---
# <a name="net-core-guide"></a><span data-ttu-id="5f7f4-104">Guía de .NET Core</span><span class="sxs-lookup"><span data-stu-id="5f7f4-104">.NET Core Guide</span></span>

<span data-ttu-id="5f7f4-105">[.NET Core](about.md) es una plataforma de desarrollo de uso general de [código abierto](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) de cuyo mantenimiento se encargan Microsoft y la comunidad .NET en [GitHub](https://github.com/dotnet/core).</span><span class="sxs-lookup"><span data-stu-id="5f7f4-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="5f7f4-106">Es multiplataforma, admite Windows, macOS y Linux y puede usarse para compilar aplicaciones de dispositivo, nube e IoT.</span><span class="sxs-lookup"><span data-stu-id="5f7f4-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

<span data-ttu-id="5f7f4-107">Consulte [Acerca de .NET Core](about.md) para más información sobre .NET Core, incluidas sus características, idiomas y marcos admitidos y principales API.</span><span class="sxs-lookup"><span data-stu-id="5f7f4-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="5f7f4-108">Consulte los [tutoriales de .NET Core](tutorials/index.md) para aprender a crear una aplicación .NET Core sencilla.</span><span class="sxs-lookup"><span data-stu-id="5f7f4-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="5f7f4-109">En unos minutos su primera aplicación estará lista y funcionando.</span><span class="sxs-lookup"><span data-stu-id="5f7f4-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="5f7f4-110">Si quiere probar .NET Core en su explorador, consulte el tutorial en línea [Números en C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml).</span><span class="sxs-lookup"><span data-stu-id="5f7f4-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) online tutorial.</span></span>

## <a name="download-net-core"></a><span data-ttu-id="5f7f4-111">Descarga de .NET Core</span><span class="sxs-lookup"><span data-stu-id="5f7f4-111">Download .NET Core</span></span>

<span data-ttu-id="5f7f4-112">Descargue el [SDK de .NET Core](https://www.microsoft.com/net/download) para probar .NET Core en su máquina Windows, macOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="5f7f4-112">Download the [.NET Core SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="5f7f4-113">Si prefiere usar contenedores de Docker, visite [Docker Hub de .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="5f7f4-113">And if you prefer to use Docker containers, visit the [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span>

<span data-ttu-id="5f7f4-114">Si busca otra versión de .NET Core, todas las versiones de .NET Core están disponibles en la [página de descargas de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="5f7f4-114">All .NET Core versions are available at [.NET Core Downloads](https://dotnet.microsoft.com/download/dotnet-core) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-31"></a><span data-ttu-id="5f7f4-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="5f7f4-115">.NET Core 3.1</span></span>

<span data-ttu-id="5f7f4-116">La última versión es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="5f7f4-116">The latest version is .NET Core 3.1.</span></span> <span data-ttu-id="5f7f4-117">Esto incluye mejoras menores con respecto a .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="5f7f4-117">Which includes minor improvements over .NET Core 3.0.</span></span> <span data-ttu-id="5f7f4-118">Pero .NET Core 3.1 es una versión admitida a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="5f7f4-118">However, .NET Core 3.1 is a long-term supported release.</span></span> <span data-ttu-id="5f7f4-119">Para más información sobre la versión .NET Core 3.1, vea [Novedades de .NET Core 3.1](./whats-new/dotnet-core-3-1.md).</span><span class="sxs-lookup"><span data-stu-id="5f7f4-119">For more information about the .NET Core 3.1 release, see [What's new in .NET Core 3.1](./whats-new/dotnet-core-3-1.md).</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="5f7f4-120">Creación de la primera aplicación</span><span class="sxs-lookup"><span data-stu-id="5f7f4-120">Create your first application</span></span>

<span data-ttu-id="5f7f4-121">Después de instalar el SDK de .NET Core, abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="5f7f4-121">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="5f7f4-122">Escriba los comandos `dotnet` siguientes para crear y ejecutar una aplicación C#:</span><span class="sxs-lookup"><span data-stu-id="5f7f4-122">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="5f7f4-123">Debería ver los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="5f7f4-123">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="support"></a><span data-ttu-id="5f7f4-124">Soporte técnico</span><span class="sxs-lookup"><span data-stu-id="5f7f4-124">Support</span></span>

<span data-ttu-id="5f7f4-125">[Microsoft admite](https://dotnet.microsoft.com/platform/support/policy) .NET Core en Windows, macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="5f7f4-125">.NET Core is [supported by Microsoft](https://dotnet.microsoft.com/platform/support/policy), on Windows, macOS, and Linux.</span></span> <span data-ttu-id="5f7f4-126">Varias veces al año, por lo general mensualmente, se actualiza para aumentar la seguridad y la calidad.</span><span class="sxs-lookup"><span data-stu-id="5f7f4-126">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="5f7f4-127">Las distribuciones binarias de .NET Core se compilan y prueban en servidores mantenidos por Microsoft en Azure y reciben el mismo soporte técnico que cualquier otro producto de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5f7f4-127">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="5f7f4-128">[Red Hat admite .NET Core](http://redhatloves.net/) en Red Hat Enterprise Linux (RHEL).</span><span class="sxs-lookup"><span data-stu-id="5f7f4-128">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="5f7f4-129">Red Hat compila .NET Core desde el código fuente y permite que esté disponible en [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span><span class="sxs-lookup"><span data-stu-id="5f7f4-129">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="5f7f4-130">Red Hat y Microsoft colaboran para asegurarse de que .NET Core funciona bien en RHEL.</span><span class="sxs-lookup"><span data-stu-id="5f7f4-130">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
