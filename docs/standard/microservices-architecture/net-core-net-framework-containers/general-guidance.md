---
title: Instrucciones generales
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Instrucciones generales
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 22dea926e77079e4f543934613ced13a28b2dae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="general-guidance"></a><span data-ttu-id="97fe3-104">Instrucciones generales</span><span class="sxs-lookup"><span data-stu-id="97fe3-104">General guidance</span></span>

<span data-ttu-id="97fe3-105">En esta sección se proporciona un resumen de cuándo se debe elegir .NET Core o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="97fe3-105">This section provides a summary of when to choose .NET Core or .NET Framework.</span></span> <span data-ttu-id="97fe3-106">Se proporcionan más detalles acerca de estas opciones en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="97fe3-106">We provide more details about these choices in the sections that follow.</span></span>

<span data-ttu-id="97fe3-107">Debe utilizar .NET Core, con Linux o contenedores de Windows para la aplicación de servidor en contenedores de Docker cuando:</span><span class="sxs-lookup"><span data-stu-id="97fe3-107">You should use .NET Core, with Linux or Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="97fe3-108">Tenga necesidades multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="97fe3-108">You have cross-platform needs.</span></span> <span data-ttu-id="97fe3-109">Por ejemplo, desea utilizar contenedores de Windows y Linux.</span><span class="sxs-lookup"><span data-stu-id="97fe3-109">For example, you want to use both Linux and Windows Containers.</span></span>

-   <span data-ttu-id="97fe3-110">La arquitectura de la aplicación se basa en microservicios.</span><span class="sxs-lookup"><span data-stu-id="97fe3-110">Your application architecture is based on microservices.</span></span>

-   <span data-ttu-id="97fe3-111">Debe iniciar contenedores rápido y desea una pequeña superficie por contenedor para lograr una mejor densidad o más contenedores por unidad de hardware con el fin de reducir los costos.</span><span class="sxs-lookup"><span data-stu-id="97fe3-111">You need to start containers fast and want a small footprint per container to achieve better density or more containers per hardware unit in order to lower your costs.</span></span>

<span data-ttu-id="97fe3-112">En resumen, al crear nuevas aplicaciones de .NET en contenedores, se debe considerar .NET Core como la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="97fe3-112">In short, when you create new containerized .NET applications, you should consider .NET Core as the default choice.</span></span> <span data-ttu-id="97fe3-113">Tiene muchas ventajas y mejor se adapte a la filosofía de contenedores y el estilo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97fe3-113">It has many benefits and fits best with the containers philosophy and style of working.</span></span>

<span data-ttu-id="97fe3-114">Otra ventaja adicional del uso de .NET Core es que puede ejecutar en paralelo versiones de .NET para aplicaciones en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="97fe3-114">An additional benefit of using .NET Core is that you can run side by side .NET versions for applications within the same machine.</span></span> <span data-ttu-id="97fe3-115">Esta ventaja es más importante para servidores o máquinas virtuales que no usan contenedores, porque contenedores aislar las versiones de .NET que necesita la aplicación.</span><span class="sxs-lookup"><span data-stu-id="97fe3-115">This benefit is more important for servers or VMs that do not use containers, because containers isolate the versions of .NET that the app needs.</span></span> <span data-ttu-id="97fe3-116">(Siempre que sean compatibles con el sistema operativo subyacente.)</span><span class="sxs-lookup"><span data-stu-id="97fe3-116">(As long as they are compatible with the underlying OS.)</span></span>

<span data-ttu-id="97fe3-117">Debe utilizar .NET Framework, con los contenedores de Windows, para la aplicación de servidor en contenedores de Docker cuando:</span><span class="sxs-lookup"><span data-stu-id="97fe3-117">You should use .NET Framework, with Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="97fe3-118">Actualmente, la aplicación utiliza .NET Framework y tiene fuertes dependencias en Windows.</span><span class="sxs-lookup"><span data-stu-id="97fe3-118">Your application currently uses .NET Framework and has strong dependencies on Windows.</span></span>

-   <span data-ttu-id="97fe3-119">Debe usar las API de Windows que no son compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="97fe3-119">You need to use Windows APIs that are not supported by .NET Core.</span></span>

-   <span data-ttu-id="97fe3-120">Debe usar las bibliotecas .NET de terceros o paquetes de NuGet que no están disponibles para .NET Core.</span><span class="sxs-lookup"><span data-stu-id="97fe3-120">You need to use third-party .NET libraries or NuGet packages that are not available for .NET Core.</span></span>

<span data-ttu-id="97fe3-121">Uso de .NET Framework en Docker puede mejorar sus experiencias de implementación minimizar los problemas de implementación.</span><span class="sxs-lookup"><span data-stu-id="97fe3-121">Using .NET Framework on Docker can improve your deployment experiences by minimizing deployment issues.</span></span> <span data-ttu-id="97fe3-122">Esto [ *escenario "Levantar y mover"* ](https://aka.ms/liftandshiftwithcontainersebook) es importante para containerizing aplicaciones heredadas que se desarrollaron originalmente con .NET Framework tradicionales, como formularios Web Forms de ASP.NET, MVC web WCF (o aplicaciones Servicios de Windows Communication Foundation).</span><span class="sxs-lookup"><span data-stu-id="97fe3-122">This [*"lift and shift" scenario*](https://aka.ms/liftandshiftwithcontainersebook) is important for containerizing legacy applications that were originally developed with the traditional .NET Framework, like ASP.NET WebForms, MVC web apps or WCF (Windows Communication Foundation) services.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="97fe3-123">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="97fe3-123">Additional resources</span></span>

-   <span data-ttu-id="97fe3-124">**libro electrónico: modernizar las aplicaciones existentes de .NET Framework con contenedores de Windows y Azure**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span><span class="sxs-lookup"><span data-stu-id="97fe3-124">**e-book: Modernize existing .NET Framework applications with Azure and Windows Containers**
[*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span></span>

-   <span data-ttu-id="97fe3-125">**Aplicaciones de ejemplo: modernización de las aplicaciones web ASP.NET heredadas mediante el uso de contenedores de Windows**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span><span class="sxs-lookup"><span data-stu-id="97fe3-125">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers**
[*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="97fe3-126">[Anterior] (index.md) [siguiente] (net-core-contenedor-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="97fe3-126">[Previous] (index.md) [Next] (net-core-container-scenarios.md)</span></span>
