---
title: Guía de .NET Core
description: .NET Core es una implementación modular y de alto rendimiento de .NET para crear aplicaciones de Windows, Linux y Mac. Obtenga información sobre .NET Core para comenzar.
author: richlander
ms.date: 09/23/2019
ms.custom: updateeachrelease
ms.openlocfilehash: 95f18ca09852ce139a4b99ed7aef4802d4883e13
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216220"
---
# <a name="net-core-guide"></a><span data-ttu-id="d5d56-104">Guía de .NET Core</span><span class="sxs-lookup"><span data-stu-id="d5d56-104">.NET Core Guide</span></span>

<span data-ttu-id="d5d56-105">[.NET Core](about.md) es una plataforma de desarrollo de uso general de [código abierto](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) de cuyo mantenimiento se encargan Microsoft y la comunidad .NET en [GitHub](https://github.com/dotnet/core).</span><span class="sxs-lookup"><span data-stu-id="d5d56-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="d5d56-106">Es multiplataforma, admite Windows, macOS y Linux y puede usarse para compilar aplicaciones de dispositivo, nube e IoT.</span><span class="sxs-lookup"><span data-stu-id="d5d56-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

<span data-ttu-id="d5d56-107">Consulte [Acerca de .NET Core](about.md) para más información sobre .NET Core, incluidas sus características, idiomas y marcos admitidos y principales API.</span><span class="sxs-lookup"><span data-stu-id="d5d56-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="d5d56-108">Consulte los [tutoriales de .NET Core](tutorials/index.md) para aprender a crear una aplicación .NET Core sencilla.</span><span class="sxs-lookup"><span data-stu-id="d5d56-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="d5d56-109">En unos minutos su primera aplicación estará lista y funcionando.</span><span class="sxs-lookup"><span data-stu-id="d5d56-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="d5d56-110">Si quiere probar .NET Core en su explorador, consulte el tutorial en línea [Números en C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml).</span><span class="sxs-lookup"><span data-stu-id="d5d56-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) online tutorial.</span></span>

## <a name="download-net-core"></a><span data-ttu-id="d5d56-111">Descarga de .NET Core</span><span class="sxs-lookup"><span data-stu-id="d5d56-111">Download .NET Core</span></span>

<span data-ttu-id="d5d56-112">Descargue el [SDK de .NET Core](https://www.microsoft.com/net/download) para probar .NET Core en su máquina Windows, macOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="d5d56-112">Download the [.NET Core SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="d5d56-113">Si prefiere usar contenedores de Docker, visite [Docker Hub de .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="d5d56-113">And if you prefer to use Docker containers, visit the [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span>

<span data-ttu-id="d5d56-114">Si busca otra versión de .NET Core, todas las versiones de .NET Core están disponibles en la [página de descargas de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="d5d56-114">All .NET Core versions are available at [.NET Core Downloads](https://dotnet.microsoft.com/download/dotnet-core) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-30"></a><span data-ttu-id="d5d56-115">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d5d56-115">.NET Core 3.0</span></span>

<span data-ttu-id="d5d56-116">La última versión es .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d5d56-116">The latest version is .NET Core 3.0.</span></span> <span data-ttu-id="d5d56-117">Entre las nuevas características se incluye la compatibilidad del escritorio de Windows con Windows Presentation Foundation (WPF) y Windows Forms, el desarrollo web de C# de pila completa con Blazor, nuevas mejoras en SignalR y Azure SignalR Service, nuevas características del lenguaje C# 8 y mucho más.</span><span class="sxs-lookup"><span data-stu-id="d5d56-117">New features include Windows Desktop support with Windows Presentation Foundation (WPF) and Windows Forms, full stack C# web development with Blazor, new enhancements to SignalR and Azure SignalR Service, new C# language features with C# 8, and much more.</span></span> <span data-ttu-id="d5d56-118">Para ver un listado completo de las nuevas características de .NET Core 3.0, consulte [Novedades de .NET Core 3.0](./whats-new/dotnet-core-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="d5d56-118">For a full listing of the new features in .NET Core 3.0, see [What's new in .NET Core 3.0](./whats-new/dotnet-core-3-0.md).</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="d5d56-119">Creación de la primera aplicación</span><span class="sxs-lookup"><span data-stu-id="d5d56-119">Create your first application</span></span>

<span data-ttu-id="d5d56-120">Después de instalar el SDK de .NET Core, abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="d5d56-120">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="d5d56-121">Escriba los comandos `dotnet` siguientes para crear y ejecutar una aplicación C#:</span><span class="sxs-lookup"><span data-stu-id="d5d56-121">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="d5d56-122">Debería ver los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="d5d56-122">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="support"></a><span data-ttu-id="d5d56-123">Soporte técnico</span><span class="sxs-lookup"><span data-stu-id="d5d56-123">Support</span></span>

<span data-ttu-id="d5d56-124">[Microsoft admite](https://dotnet.microsoft.com/platform/support/policy) .NET Core en Windows, macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="d5d56-124">.NET Core is [supported by Microsoft](https://dotnet.microsoft.com/platform/support/policy), on Windows, macOS, and Linux.</span></span> <span data-ttu-id="d5d56-125">Varias veces al año, por lo general mensualmente, se actualiza para aumentar la seguridad y la calidad.</span><span class="sxs-lookup"><span data-stu-id="d5d56-125">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="d5d56-126">Las distribuciones binarias de .NET Core se compilan y prueban en servidores mantenidos por Microsoft en Azure y reciben el mismo soporte técnico que cualquier otro producto de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5d56-126">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="d5d56-127">[Red Hat admite .NET Core](http://redhatloves.net/) en Red Hat Enterprise Linux (RHEL).</span><span class="sxs-lookup"><span data-stu-id="d5d56-127">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="d5d56-128">Red Hat compila .NET Core desde el código fuente y permite que esté disponible en [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span><span class="sxs-lookup"><span data-stu-id="d5d56-128">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="d5d56-129">Red Hat y Microsoft colaboran para asegurarse de que .NET Core funciona bien en RHEL.</span><span class="sxs-lookup"><span data-stu-id="d5d56-129">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
