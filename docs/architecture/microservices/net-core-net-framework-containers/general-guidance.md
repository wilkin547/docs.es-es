---
title: Orientación general
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Orientación general
ms.date: 09/11/2018
ms.openlocfilehash: e3bb4b8cf3e371c31d783fe4cfafeac282fb72b8
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144570"
---
# <a name="general-guidance"></a><span data-ttu-id="e6b62-103">Orientación general</span><span class="sxs-lookup"><span data-stu-id="e6b62-103">General guidance</span></span>

<span data-ttu-id="e6b62-104">En esta sección se proporciona un resumen de cuándo es mejor elegir .NET Core y cuándo es preferible .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6b62-104">This section provides a summary of when to choose .NET Core or .NET Framework.</span></span> <span data-ttu-id="e6b62-105">Se proporcionan más detalles acerca de estas opciones en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="e6b62-105">We provide more details about these choices in the sections that follow.</span></span>

<span data-ttu-id="e6b62-106">Se recomienda utilizar .NET Core con contenedores de Linux o Windows en la aplicación de servidor Docker en contenedor cuando:</span><span class="sxs-lookup"><span data-stu-id="e6b62-106">You should use .NET Core, with Linux or Windows Containers, for your containerized Docker server application when:</span></span>

- <span data-ttu-id="e6b62-107">Tenga necesidades multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="e6b62-107">You have cross-platform needs.</span></span> <span data-ttu-id="e6b62-108">Por ejemplo, si quiere utilizar contenedores de Linux y Windows.</span><span class="sxs-lookup"><span data-stu-id="e6b62-108">For example, you want to use both Linux and Windows Containers.</span></span>

- <span data-ttu-id="e6b62-109">La arquitectura de la aplicación esté basada en microservicios.</span><span class="sxs-lookup"><span data-stu-id="e6b62-109">Your application architecture is based on microservices.</span></span>

- <span data-ttu-id="e6b62-110">Necesite iniciar contenedores rápidamente y quiera que una pequeña superficie por contenedor alcance una mejor densidad o más contenedores por unidad de hardware con el fin de reducir costos.</span><span class="sxs-lookup"><span data-stu-id="e6b62-110">You need to start containers fast and want a small footprint per container to achieve better density or more containers per hardware unit in order to lower your costs.</span></span>

<span data-ttu-id="e6b62-111">En resumen, al crear nuevas aplicaciones .NET en contenedores, debe optar por .NET Core como opción predeterminada,</span><span class="sxs-lookup"><span data-stu-id="e6b62-111">In short, when you create new containerized .NET applications, you should consider .NET Core as the default choice.</span></span> <span data-ttu-id="e6b62-112">ya que esta opción presenta muchas ventajas y es la que mejor se adapta a la filosofía y al estilo de trabajo de los contenedores.</span><span class="sxs-lookup"><span data-stu-id="e6b62-112">It has many benefits and fits best with the containers philosophy and style of working.</span></span>

<span data-ttu-id="e6b62-113">Otra ventaja adicional de usar .NET Core es que puede ejecutar versiones paralelas de .NET para aplicaciones en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="e6b62-113">An additional benefit of using .NET Core is that you can run side by side .NET versions for applications within the same machine.</span></span> <span data-ttu-id="e6b62-114">Esta ventaja es más importante para servidores o máquinas virtuales que no utilizan contenedores, porque los contenedores aíslan las versiones de .NET que necesita la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e6b62-114">This benefit is more important for servers or VMs that do not use containers, because containers isolate the versions of .NET that the app needs.</span></span> <span data-ttu-id="e6b62-115">(Siempre que sean compatibles con el sistema operativo subyacente).</span><span class="sxs-lookup"><span data-stu-id="e6b62-115">(As long as they are compatible with the underlying OS.)</span></span>

<span data-ttu-id="e6b62-116">Se recomienda utilizar .NET Framework en la aplicación de servidor Docker en contenedor cuando:</span><span class="sxs-lookup"><span data-stu-id="e6b62-116">You should use .NET Framework for your containerized Docker server application when:</span></span>

- <span data-ttu-id="e6b62-117">La aplicación ya utilice .NET Framework y dependa fuertemente de Windows.</span><span class="sxs-lookup"><span data-stu-id="e6b62-117">Your application currently uses .NET Framework and has strong dependencies on Windows.</span></span>

- <span data-ttu-id="e6b62-118">Tenga que usar API de Windows que no sean compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e6b62-118">You need to use Windows APIs that are not supported by .NET Core.</span></span>

- <span data-ttu-id="e6b62-119">Necesite usar bibliotecas .NET de terceros o paquetes NuGet que no estén disponibles para .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e6b62-119">You need to use third-party .NET libraries or NuGet packages that are not available for .NET Core.</span></span>

<span data-ttu-id="e6b62-120">Utilizar .NET Framework en Docker puede mejorar sus experiencias de implementación minimizando los problemas de implementación.</span><span class="sxs-lookup"><span data-stu-id="e6b62-120">Using .NET Framework on Docker can improve your deployment experiences by minimizing deployment issues.</span></span> <span data-ttu-id="e6b62-121">Este [escenario de migración mediante lift-and-shift](https://aka.ms/liftandshiftwithcontainersebook) es importante para aplicaciones en contenedor heredadas que se desarrollaron originalmente con .NET Framework, como formularios web de ASP.NET, aplicaciones web MVC o servicios de WCF (Windows Communication Foundation).</span><span class="sxs-lookup"><span data-stu-id="e6b62-121">This ["lift and shift" scenario](https://aka.ms/liftandshiftwithcontainersebook) is important for containerizing legacy applications that were originally developed with the traditional .NET Framework, like ASP.NET WebForms, MVC web apps or WCF (Windows Communication Foundation) services.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="e6b62-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e6b62-122">Additional resources</span></span>

- <span data-ttu-id="e6b62-123">**Libro electrónico: Modernize existing .NET Framework applications with Azure and Windows Containers** (Libro electrónico: Modernización de las aplicaciones .NET Framework existentes con contenedores de Azure y de Windows)</span><span class="sxs-lookup"><span data-stu-id="e6b62-123">**E-book: Modernize existing .NET Framework applications with Azure and Windows Containers**</span></span>  
    <https://aka.ms/liftandshiftwithcontainersebook>

- <span data-ttu-id="e6b62-124">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers** (Aplicaciones de ejemplo: Modernización de aplicaciones web de ASP.NET heredadas mediante contenedores de Windows)</span><span class="sxs-lookup"><span data-stu-id="e6b62-124">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers**</span></span>  
    <https://aka.ms/eshopmodernizing>

>[!div class="step-by-step"]
><span data-ttu-id="e6b62-125">[Anterior](index.md)
>[Siguiente](net-core-container-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="e6b62-125">[Previous](index.md)
[Next](net-core-container-scenarios.md)</span></span>
