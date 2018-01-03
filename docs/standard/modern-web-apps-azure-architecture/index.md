---
title: "Diseño de aplicaciones web modernas con ASP.NET Core y Azure"
description: "Diseño de aplicaciones web modernas con ASP.NET Core y Azure | Introducción"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 44864274a86634c0199885b5507124f2f54ce0f6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="848d2-103">Diseño de aplicaciones web modernas con ASP.NET Core y Azure</span><span class="sxs-lookup"><span data-stu-id="848d2-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

<span data-ttu-id="848d2-104">.NET Core y ASP.NET Core ofrecen varias ventajas con respecto al desarrollo tradicional con .NET.</span><span class="sxs-lookup"><span data-stu-id="848d2-104">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="848d2-105">Debe usar .NET Core para las aplicaciones de servidor si algunos o todos los elementos siguientes son importantes para el éxito de su aplicación:</span><span class="sxs-lookup"><span data-stu-id="848d2-105">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

-   <span data-ttu-id="848d2-106">Compatibilidad entre plataformas</span><span class="sxs-lookup"><span data-stu-id="848d2-106">Cross-platform support</span></span>

-   <span data-ttu-id="848d2-107">Uso de microservicios</span><span class="sxs-lookup"><span data-stu-id="848d2-107">Use of microservices</span></span>

-   <span data-ttu-id="848d2-108">Uso de contenedores de Docker</span><span class="sxs-lookup"><span data-stu-id="848d2-108">Use of Docker containers</span></span>

-   <span data-ttu-id="848d2-109">Requisitos elevados de rendimiento y escalabilidad</span><span class="sxs-lookup"><span data-stu-id="848d2-109">High performance and scalability requirements</span></span>

-   <span data-ttu-id="848d2-110">Control de versiones en paralelo de versiones de .NET por aplicación en el mismo servidor</span><span class="sxs-lookup"><span data-stu-id="848d2-110">Side-by-side versioning of .NET versions by application on the same server</span></span>

<span data-ttu-id="848d2-111">Las aplicaciones tradicionales de .NET son compatibles con estos requisitos, pero ASP.NET Core y .NET Core se han optimizado para ofrecer una compatibilidad mejorada para los escenarios anteriores.</span><span class="sxs-lookup"><span data-stu-id="848d2-111">Traditional .NET applications can and do support these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="848d2-112">Cada vez más organizaciones deciden hospedar sus aplicaciones web en la nube con servicios como Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="848d2-112">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="848d2-113">Considere la posibilidad de hospedar su aplicación en la nube si los siguientes elementos son importantes para la aplicación o la organización:</span><span class="sxs-lookup"><span data-stu-id="848d2-113">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

-   <span data-ttu-id="848d2-114">Inversión reducida en costos de centros de datos (hardware, software, espacio, utilidades, etc.)</span><span class="sxs-lookup"><span data-stu-id="848d2-114">Reduced investment in data center costs (hardware, software, space, utilities, etc)</span></span>

-   <span data-ttu-id="848d2-115">Precios flexibles (pago en función del uso, y no por la capacidad inactiva)</span><span class="sxs-lookup"><span data-stu-id="848d2-115">Flexible pricing (pay based on usage, not for idle capacity)</span></span>

-   <span data-ttu-id="848d2-116">Confiabilidad extrema</span><span class="sxs-lookup"><span data-stu-id="848d2-116">Extreme reliability</span></span>

-   <span data-ttu-id="848d2-117">Movilidad mejorada de la aplicación; modificación sencilla de dónde y cómo implementar la aplicación</span><span class="sxs-lookup"><span data-stu-id="848d2-117">Improved app mobility; easily change where and how your app is deployed</span></span>

-   <span data-ttu-id="848d2-118">Capacidad flexible; escalado o reducción vertical en función de las necesidades reales</span><span class="sxs-lookup"><span data-stu-id="848d2-118">Flexible capacity; scale up or down based on actual needs</span></span>

<span data-ttu-id="848d2-119">La compilación de aplicaciones web con ASP.NET Core, hospedadas en Microsoft Azure, ofrece numerosas ventajas competitivas con respecto a las alternativas tradicionales.</span><span class="sxs-lookup"><span data-stu-id="848d2-119">Building web applications with ASP.NET Core, hosted in Microsoft Azure, offers numerous competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="848d2-120">Se ha optimizado ASP.NET Core para escenarios de hospedaje en la nube y prácticas de desarrollo de aplicaciones web modernas.</span><span class="sxs-lookup"><span data-stu-id="848d2-120">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="848d2-121">En esta guía se ofrece información sobre cómo diseñar aplicaciones con ASP.NET Core para sacar el máximo provecho de estas funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="848d2-121">In this guide, you will learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="purpose"></a><span data-ttu-id="848d2-122">Propósito</span><span class="sxs-lookup"><span data-stu-id="848d2-122">Purpose</span></span>

<span data-ttu-id="848d2-123">En esta guía se proporcionan instrucciones de un extremo a otro sobre cómo compilar aplicaciones web monolíticas con ASP.NET Core y Azure.</span><span class="sxs-lookup"><span data-stu-id="848d2-123">This guide provides end-to-end guidance on building monolithic web applications using ASP.NET Core and Azure.</span></span>

<span data-ttu-id="848d2-124">Esta guía es complementaria a "*Diseño y desarrollo de aplicaciones basadas en contenedores y microservicios con .NET*", que se centra más en Docker, los microservicios y el desarrollo de contenedores para hospedar aplicaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="848d2-124">This guide is complementary to the "*Architecting and Developing Containerized and Microservice-based Applications with .NET*" which focuses more on Docker, Microservices, and Deployment of Containers to host enterprise applications.</span></span>

> ### <a name="architecting-and-developing-containerized-microservice-based-apps-in-net"></a><span data-ttu-id="848d2-125">Diseño y desarrollo de aplicaciones basadas en contenedores y microservicios con .NET</span><span class="sxs-lookup"><span data-stu-id="848d2-125">Architecting and Developing Containerized Microservice Based Apps in .NET</span></span>
> - <span data-ttu-id="848d2-126">**Libro electrónico**</span><span class="sxs-lookup"><span data-stu-id="848d2-126">**e-book**</span></span>  
> <span data-ttu-id="848d2-127"><http://aka.ms/MicroservicesEbook></span><span class="sxs-lookup"><span data-stu-id="848d2-127"><http://aka.ms/MicroservicesEbook></span></span>
> - <span data-ttu-id="848d2-128">**Aplicación de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="848d2-128">**Sample Application**</span></span>  
> <span data-ttu-id="848d2-129"><http://aka.ms/microservicesarchitecture></span><span class="sxs-lookup"><span data-stu-id="848d2-129"><http://aka.ms/microservicesarchitecture></span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="848d2-130">Destinatarios de esta guía</span><span class="sxs-lookup"><span data-stu-id="848d2-130">Who should use this guide</span></span>

<span data-ttu-id="848d2-131">Los destinatarios de esta guía son principalmente desarrolladores, jefes de desarrollo y arquitectos interesados en crear aplicaciones web modernas con tecnologías y servicios de Microsoft en la nube.</span><span class="sxs-lookup"><span data-stu-id="848d2-131">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="848d2-132">Otros destinatarios secundarios son los responsables de tomar decisiones técnicas que ya están familiarizados con ASP.NET o Azure y que buscan información sobre si tiene sentido actualizar a ASP.NET Core para los proyectos nuevos o existentes.</span><span class="sxs-lookup"><span data-stu-id="848d2-132">A secondary audience is technical decision makers who are already familiar ASP.NET and/or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="848d2-133">Cómo leer esta guía</span><span class="sxs-lookup"><span data-stu-id="848d2-133">How you can use this guide</span></span>

<span data-ttu-id="848d2-134">Esta guía se ha comprimido en un documento relativamente pequeño que se centra en la creación de aplicaciones web con modernas tecnologías de .NET y Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="848d2-134">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Windows Azure.</span></span> <span data-ttu-id="848d2-135">Por lo tanto, se puede leer completa para proporcionar una base de conocimiento sobre estas aplicaciones y sus consideraciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="848d2-135">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="848d2-136">La guía, junto con su aplicación de ejemplo, también puede servir como punto inicial o referencia.</span><span class="sxs-lookup"><span data-stu-id="848d2-136">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="848d2-137">Use la aplicación de ejemplo asociada como una plantilla para las aplicaciones propias o para consultar cómo se pueden organizar los componentes de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="848d2-137">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="848d2-138">Consulte los principios y la cobertura de la arquitectura, las opciones tecnológicas y las consideraciones para la toma de decisiones de esta guía a la hora de sopesar estas opciones para su propia aplicación.</span><span class="sxs-lookup"><span data-stu-id="848d2-138">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when weighing these choices for your own application.</span></span>

<span data-ttu-id="848d2-139">No dude en reenviar esta guía a su equipo para ayudarlo a garantizar una comprensión común de estas consideraciones y oportunidades.</span><span class="sxs-lookup"><span data-stu-id="848d2-139">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="848d2-140">El hecho de que todos los usuarios trabajen a partir de un conjunto común de principios subyacentes y terminología ayudará a garantizar una aplicación coherente de las prácticas y los patrones de diseño.</span><span class="sxs-lookup"><span data-stu-id="848d2-140">Having everybody working from a common set of terminology and underlying principles will help ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="848d2-141">Referencias</span><span class="sxs-lookup"><span data-stu-id="848d2-141">References</span></span>
- <span data-ttu-id="848d2-142">**Selección entre .NET Core y .NET Framework para aplicaciones de servidor**</span><span class="sxs-lookup"><span data-stu-id="848d2-142">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
<span data-ttu-id="848d2-143"><https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server></span><span class="sxs-lookup"><span data-stu-id="848d2-143"><https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="848d2-144">[Siguiente] (modern-web-applications-characteristics.md)</span><span class="sxs-lookup"><span data-stu-id="848d2-144">[Next] (modern-web-applications-characteristics.md)</span></span>
