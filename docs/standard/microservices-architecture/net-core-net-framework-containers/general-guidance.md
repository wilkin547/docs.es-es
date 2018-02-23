---
title: "Orientación general"
description: "Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Orientación general"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fa58d1d81b2d1523baf123d4963db2ca00fee15d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="general-guidance"></a><span data-ttu-id="2dde8-104">Orientación general</span><span class="sxs-lookup"><span data-stu-id="2dde8-104">General guidance</span></span>

<span data-ttu-id="2dde8-105">En esta sección se proporciona un resumen de cuándo es mejor elegir .NET Core y cuándo es preferible .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2dde8-105">This section provides a summary of when to choose .NET Core or .NET Framework.</span></span> <span data-ttu-id="2dde8-106">Se proporcionan más detalles acerca de estas opciones en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="2dde8-106">We provide more details about these choices in the sections that follow.</span></span>

<span data-ttu-id="2dde8-107">Se recomienda utilizar .NET Core con contenedores de Linux o Windows en la aplicación de servidor Docker en contenedor cuando:</span><span class="sxs-lookup"><span data-stu-id="2dde8-107">You should use .NET Core, with Linux or Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="2dde8-108">Tenga necesidades multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="2dde8-108">You have cross-platform needs.</span></span> <span data-ttu-id="2dde8-109">Por ejemplo, si quiere utilizar contenedores de Linux y Windows.</span><span class="sxs-lookup"><span data-stu-id="2dde8-109">For example, you want to use both Linux and Windows Containers.</span></span>

-   <span data-ttu-id="2dde8-110">La arquitectura de la aplicación esté basada en microservicios.</span><span class="sxs-lookup"><span data-stu-id="2dde8-110">Your application architecture is based on microservices.</span></span>

-   <span data-ttu-id="2dde8-111">Necesite iniciar contenedores rápidamente y quiera que una pequeña superficie por contenedor alcance una mejor densidad o más contenedores por unidad de hardware con el fin de reducir costos.</span><span class="sxs-lookup"><span data-stu-id="2dde8-111">You need to start containers fast and want a small footprint per container to achieve better density or more containers per hardware unit in order to lower your costs.</span></span>

<span data-ttu-id="2dde8-112">En resumen, al crear nuevas aplicaciones .NET en contenedores, debe optar por .NET Core como opción predeterminada,</span><span class="sxs-lookup"><span data-stu-id="2dde8-112">In short, when you create new containerized .NET applications, you should consider .NET Core as the default choice.</span></span> <span data-ttu-id="2dde8-113">ya que esta opción presenta muchas ventajas y es la que mejor se adapta a la filosofía y al estilo de trabajo de los contenedores.</span><span class="sxs-lookup"><span data-stu-id="2dde8-113">It has many benefits and fits best with the containers philosophy and style of working.</span></span>

<span data-ttu-id="2dde8-114">Otra ventaja adicional de usar .NET Core es que puede ejecutar versiones paralelas de .NET para aplicaciones en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="2dde8-114">An additional benefit of using .NET Core is that you can run side by side .NET versions for applications within the same machine.</span></span> <span data-ttu-id="2dde8-115">Esta ventaja es más importante para servidores o máquinas virtuales que no utilizan contenedores, porque los contenedores aíslan las versiones de .NET que necesita la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2dde8-115">This benefit is more important for servers or VMs that do not use containers, because containers isolate the versions of .NET that the app needs.</span></span> <span data-ttu-id="2dde8-116">(Siempre que sean compatibles con el sistema operativo subyacente).</span><span class="sxs-lookup"><span data-stu-id="2dde8-116">(As long as they are compatible with the underlying OS.)</span></span>

<span data-ttu-id="2dde8-117">Se recomienda utilizar .NET Framework con contenedores de Windows en la aplicación de servidor Docker en contenedor cuando:</span><span class="sxs-lookup"><span data-stu-id="2dde8-117">You should use .NET Framework, with Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="2dde8-118">La aplicación ya utilice .NET Framework y dependa fuertemente de Windows.</span><span class="sxs-lookup"><span data-stu-id="2dde8-118">Your application currently uses .NET Framework and has strong dependencies on Windows.</span></span>

-   <span data-ttu-id="2dde8-119">Tenga que usar API de Windows que no sean compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2dde8-119">You need to use Windows APIs that are not supported by .NET Core.</span></span>

-   <span data-ttu-id="2dde8-120">Necesite usar bibliotecas .NET de terceros o paquetes NuGet que no estén disponibles para .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2dde8-120">You need to use third-party .NET libraries or NuGet packages that are not available for .NET Core.</span></span>

<span data-ttu-id="2dde8-121">Utilizar .NET Framework en Docker puede mejorar sus experiencias de implementación minimizando los problemas de implementación.</span><span class="sxs-lookup"><span data-stu-id="2dde8-121">Using .NET Framework on Docker can improve your deployment experiences by minimizing deployment issues.</span></span> <span data-ttu-id="2dde8-122">Este [*escenario de migración mediante lift-and-shift*](https://aka.ms/liftandshiftwithcontainersebook) es importante para aplicaciones en contenedor heredadas que se desarrollaron originalmente con .NET Framework, como formularios web de ASP.NET, aplicaciones web MVC o servicios de WCF (Windows Communication Foundation).</span><span class="sxs-lookup"><span data-stu-id="2dde8-122">This [*"lift and shift" scenario*](https://aka.ms/liftandshiftwithcontainersebook) is important for containerizing legacy applications that were originally developed with the traditional .NET Framework, like ASP.NET WebForms, MVC web apps or WCF (Windows Communication Foundation) services.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="2dde8-123">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2dde8-123">Additional resources</span></span>

-   <span data-ttu-id="2dde8-124">**Libro electrónico: Modernize existing .NET Framework applications with Azure and Windows Containers** (Modernizar aplicaciones de .NET Framework existentes con Azure y contenedores de Windows)
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span><span class="sxs-lookup"><span data-stu-id="2dde8-124">**e-book: Modernize existing .NET Framework applications with Azure and Windows Containers**
[*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span></span>

-   <span data-ttu-id="2dde8-125">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers** (Aplicaciones de ejemplo: modernización de aplicaciones web de ASP.NET heredadas mediante el uso de contenedores de Windows)
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span><span class="sxs-lookup"><span data-stu-id="2dde8-125">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers**
[*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="2dde8-126">[Anterior] (index.md) [Siguiente] (net-core-container-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="2dde8-126">[Previous] (index.md) [Next] (net-core-container-scenarios.md)</span></span>
