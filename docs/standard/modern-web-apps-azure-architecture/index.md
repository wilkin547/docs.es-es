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
ms.openlocfilehash: 1140a18aba685f3415d7c599d1b76648bf9924e7
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2018
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="6a3e4-103">Diseño de aplicaciones web modernas con ASP.NET Core y Azure</span><span class="sxs-lookup"><span data-stu-id="6a3e4-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![imagen de portada](./media/cover.jpg)


<span data-ttu-id="6a3e4-105">.NET Core y ASP.NET Core ofrecen varias ventajas con respecto al desarrollo tradicional con .NET.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-105">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="6a3e4-106">Debe usar .NET Core para las aplicaciones de servidor si algunos o todos los elementos siguientes son importantes para el éxito de su aplicación:</span><span class="sxs-lookup"><span data-stu-id="6a3e4-106">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

-   <span data-ttu-id="6a3e4-107">Compatibilidad entre plataformas</span><span class="sxs-lookup"><span data-stu-id="6a3e4-107">Cross-platform support</span></span>

-   <span data-ttu-id="6a3e4-108">Uso de microservicios</span><span class="sxs-lookup"><span data-stu-id="6a3e4-108">Use of microservices</span></span>

-   <span data-ttu-id="6a3e4-109">Uso de contenedores de Docker</span><span class="sxs-lookup"><span data-stu-id="6a3e4-109">Use of Docker containers</span></span>

-   <span data-ttu-id="6a3e4-110">Requisitos elevados de rendimiento y escalabilidad</span><span class="sxs-lookup"><span data-stu-id="6a3e4-110">High performance and scalability requirements</span></span>

-   <span data-ttu-id="6a3e4-111">Control de versiones en paralelo de versiones de .NET por aplicación en el mismo servidor</span><span class="sxs-lookup"><span data-stu-id="6a3e4-111">Side-by-side versioning of .NET versions by application on the same server</span></span>

<span data-ttu-id="6a3e4-112">Las aplicaciones tradicionales de .NET son compatibles con estos requisitos, pero ASP.NET Core y .NET Core se han optimizado para ofrecer una compatibilidad mejorada para los escenarios anteriores.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-112">Traditional .NET applications can and do support these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="6a3e4-113">Cada vez más organizaciones deciden hospedar sus aplicaciones web en la nube con servicios como Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-113">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="6a3e4-114">Considere la posibilidad de hospedar su aplicación en la nube si los siguientes elementos son importantes para la aplicación o la organización:</span><span class="sxs-lookup"><span data-stu-id="6a3e4-114">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

-   <span data-ttu-id="6a3e4-115">Inversión reducida en costos de centros de datos (hardware, software, espacio, utilidades, etc.)</span><span class="sxs-lookup"><span data-stu-id="6a3e4-115">Reduced investment in data center costs (hardware, software, space, utilities, etc)</span></span>

-   <span data-ttu-id="6a3e4-116">Precios flexibles (pago en función del uso, y no por la capacidad inactiva)</span><span class="sxs-lookup"><span data-stu-id="6a3e4-116">Flexible pricing (pay based on usage, not for idle capacity)</span></span>

-   <span data-ttu-id="6a3e4-117">Confiabilidad extrema</span><span class="sxs-lookup"><span data-stu-id="6a3e4-117">Extreme reliability</span></span>

-   <span data-ttu-id="6a3e4-118">Movilidad mejorada de la aplicación; modificación sencilla de dónde y cómo implementar la aplicación</span><span class="sxs-lookup"><span data-stu-id="6a3e4-118">Improved app mobility; easily change where and how your app is deployed</span></span>

-   <span data-ttu-id="6a3e4-119">Capacidad flexible; escalado o reducción vertical en función de las necesidades reales</span><span class="sxs-lookup"><span data-stu-id="6a3e4-119">Flexible capacity; scale up or down based on actual needs</span></span>

<span data-ttu-id="6a3e4-120">La compilación de aplicaciones web con ASP.NET Core, hospedadas en Microsoft Azure, ofrece numerosas ventajas competitivas con respecto a las alternativas tradicionales.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-120">Building web applications with ASP.NET Core, hosted in Microsoft Azure, offers numerous competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="6a3e4-121">Se ha optimizado ASP.NET Core para escenarios de hospedaje en la nube y prácticas de desarrollo de aplicaciones web modernas.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-121">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="6a3e4-122">En esta guía se ofrece información sobre cómo diseñar aplicaciones con ASP.NET Core para sacar el máximo provecho de estas funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-122">In this guide, you will learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="purpose"></a><span data-ttu-id="6a3e4-123">Propósito</span><span class="sxs-lookup"><span data-stu-id="6a3e4-123">Purpose</span></span>

<span data-ttu-id="6a3e4-124">En esta guía se proporcionan instrucciones de un extremo a otro sobre cómo compilar aplicaciones web monolíticas con ASP.NET Core y Azure.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-124">This guide provides end-to-end guidance on building monolithic web applications using ASP.NET Core and Azure.</span></span>

<span data-ttu-id="6a3e4-125">Esta guía es complementaria a "*Diseño y desarrollo de aplicaciones basadas en contenedores y microservicios con .NET*", que se centra más en Docker, los microservicios y el desarrollo de contenedores para hospedar aplicaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-125">This guide is complementary to the "*Architecting and Developing Containerized and Microservice-based Applications with .NET*" which focuses more on Docker, Microservices, and Deployment of Containers to host enterprise applications.</span></span>

> ### <a name="architecting-and-developing-containerized-microservice-based-apps-in-net"></a><span data-ttu-id="6a3e4-126">Diseño y desarrollo de aplicaciones basadas en contenedores y microservicios con .NET</span><span class="sxs-lookup"><span data-stu-id="6a3e4-126">Architecting and Developing Containerized Microservice Based Apps in .NET</span></span>
> - <span data-ttu-id="6a3e4-127">**Libro electrónico**</span><span class="sxs-lookup"><span data-stu-id="6a3e4-127">**e-book**</span></span>  
> <http://aka.ms/MicroservicesEbook>
> - <span data-ttu-id="6a3e4-128">**Aplicación de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="6a3e4-128">**Sample Application**</span></span>  
> <http://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="6a3e4-129">Destinatarios de esta guía</span><span class="sxs-lookup"><span data-stu-id="6a3e4-129">Who should use this guide</span></span>

<span data-ttu-id="6a3e4-130">Los destinatarios de esta guía son principalmente desarrolladores, jefes de desarrollo y arquitectos interesados en crear aplicaciones web modernas con tecnologías y servicios de Microsoft en la nube.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-130">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="6a3e4-131">Otros destinatarios secundarios son los responsables de tomar decisiones técnicas que ya están familiarizados con ASP.NET o Azure y que buscan información sobre si tiene sentido actualizar a ASP.NET Core para los proyectos nuevos o existentes.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-131">A secondary audience is technical decision makers who are already familiar ASP.NET and/or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="6a3e4-132">Cómo leer esta guía</span><span class="sxs-lookup"><span data-stu-id="6a3e4-132">How you can use this guide</span></span>

<span data-ttu-id="6a3e4-133">Esta guía se ha comprimido en un documento relativamente pequeño que se centra en la creación de aplicaciones web con modernas tecnologías de .NET y Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-133">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Windows Azure.</span></span> <span data-ttu-id="6a3e4-134">Por lo tanto, se puede leer completa para proporcionar una base de conocimiento sobre estas aplicaciones y sus consideraciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-134">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="6a3e4-135">La guía, junto con su aplicación de ejemplo, también puede servir como punto inicial o referencia.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-135">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="6a3e4-136">Use la aplicación de ejemplo asociada como una plantilla para las aplicaciones propias o para consultar cómo se pueden organizar los componentes de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-136">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="6a3e4-137">Consulte los principios y la cobertura de la arquitectura, las opciones tecnológicas y las consideraciones para la toma de decisiones de esta guía a la hora de sopesar estas opciones para su propia aplicación.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-137">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when weighing these choices for your own application.</span></span>

<span data-ttu-id="6a3e4-138">No dude en reenviar esta guía a su equipo para ayudarlo a garantizar una comprensión común de estas consideraciones y oportunidades.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-138">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="6a3e4-139">El hecho de que todos los usuarios trabajen a partir de un conjunto común de principios subyacentes y terminología ayudará a garantizar una aplicación coherente de las prácticas y los patrones de diseño.</span><span class="sxs-lookup"><span data-stu-id="6a3e4-139">Having everybody working from a common set of terminology and underlying principles will help ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="6a3e4-140">Referencias</span><span class="sxs-lookup"><span data-stu-id="6a3e4-140">References</span></span>
- <span data-ttu-id="6a3e4-141">**Selección entre .NET Core y .NET Framework para aplicaciones de servidor**</span><span class="sxs-lookup"><span data-stu-id="6a3e4-141">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
<https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
<span data-ttu-id="6a3e4-142">[Siguiente] (modern-web-applications-characteristics.md)</span><span class="sxs-lookup"><span data-stu-id="6a3e4-142">[Next] (modern-web-applications-characteristics.md)</span></span>
