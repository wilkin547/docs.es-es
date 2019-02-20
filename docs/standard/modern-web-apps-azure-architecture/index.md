---
title: Diseño de aplicaciones web modernas con ASP.NET Core y Azure
description: Es una guía en la que se proporcionan instrucciones de un extremo a otro sobre cómo compilar aplicaciones web monolíticas con ASP.NET Core y Azure.
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
---

# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="8b1f4-103">Diseño de aplicaciones web modernas con ASP.NET Core y Azure</span><span class="sxs-lookup"><span data-stu-id="8b1f4-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![imagen de portada](./media/cover.png)

<span data-ttu-id="8b1f4-105">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="8b1f4-105">PUBLISHED BY</span></span>

<span data-ttu-id="8b1f4-106">Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8b1f4-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="8b1f4-107">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="8b1f4-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="8b1f4-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="8b1f4-108">One Microsoft Way</span></span>

<span data-ttu-id="8b1f4-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="8b1f4-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="8b1f4-110">Copyright © 2019 de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="8b1f4-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="8b1f4-111">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-111">All rights reserved.</span></span> <span data-ttu-id="8b1f4-112">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="8b1f4-113">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="8b1f4-114">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="8b1f4-115">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="8b1f4-116">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="8b1f4-117">Microsoft y las marcas comerciales indicadas en https://www.microsoft.com en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="8b1f4-118">Mac y macOS son marcas comerciales de Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="8b1f4-119">El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="8b1f4-120">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="8b1f4-121">Autor:</span><span class="sxs-lookup"><span data-stu-id="8b1f4-121">Author:</span></span>

> <span data-ttu-id="8b1f4-122">**Steve "ardalis" Smith**: instructor y arquitecto de software de [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="8b1f4-122">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="8b1f4-123">Editores:</span><span class="sxs-lookup"><span data-stu-id="8b1f4-123">Editors:</span></span>

> <span data-ttu-id="8b1f4-124">**Maira Wenzel**</span><span class="sxs-lookup"><span data-stu-id="8b1f4-124">**Maira Wenzel**</span></span>

## <a name="introduction"></a><span data-ttu-id="8b1f4-125">Introducción</span><span class="sxs-lookup"><span data-stu-id="8b1f4-125">Introduction</span></span>

<span data-ttu-id="8b1f4-126">.NET Core y ASP.NET Core ofrecen varias ventajas con respecto al desarrollo tradicional con .NET.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-126">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="8b1f4-127">Debe usar .NET Core para las aplicaciones de servidor si algunos o todos los elementos siguientes son importantes para el éxito de su aplicación:</span><span class="sxs-lookup"><span data-stu-id="8b1f4-127">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

- <span data-ttu-id="8b1f4-128">Compatibilidad entre plataformas.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-128">Cross-platform support.</span></span>

- <span data-ttu-id="8b1f4-129">Uso de microservicios.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-129">Use of microservices.</span></span>

- <span data-ttu-id="8b1f4-130">Uso de contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-130">Use of Docker containers.</span></span>

- <span data-ttu-id="8b1f4-131">Requisitos elevados de rendimiento y escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-131">High performance and scalability requirements.</span></span>

- <span data-ttu-id="8b1f4-132">Control de versiones en paralelo de versiones de .NET por aplicación en el mismo servidor.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-132">Side-by-side versioning of .NET versions by application on the same server.</span></span>

<span data-ttu-id="8b1f4-133">Las aplicaciones tradicionales de .NET son compatibles con muchos de estos requisitos, pero ASP.NET Core y .NET Core se han optimizado para ofrecer una compatibilidad mejorada para los escenarios anteriores.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-133">Traditional .NET applications can and do support many of these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="8b1f4-134">Cada vez más organizaciones deciden hospedar sus aplicaciones web en la nube con servicios como Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-134">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="8b1f4-135">Considere la posibilidad de hospedar su aplicación en la nube si los siguientes elementos son importantes para la aplicación o la organización:</span><span class="sxs-lookup"><span data-stu-id="8b1f4-135">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

- <span data-ttu-id="8b1f4-136">Inversión reducida en costos de centros de datos (hardware, software, espacio, utilidades, administración de servidores, etc.).</span><span class="sxs-lookup"><span data-stu-id="8b1f4-136">Reduced investment in data center costs (hardware, software, space, utilities, server management, etc.)</span></span>

- <span data-ttu-id="8b1f4-137">Precios flexibles (pago en función del uso, y no por la capacidad inactiva).</span><span class="sxs-lookup"><span data-stu-id="8b1f4-137">Flexible pricing (pay based on usage, not for idle capacity).</span></span>

- <span data-ttu-id="8b1f4-138">Confiabilidad extrema.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-138">Extreme reliability.</span></span>

- <span data-ttu-id="8b1f4-139">Movilidad mejorada de la aplicación; modificación sencilla de dónde y cómo implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-139">Improved app mobility; easily change where and how your app is deployed.</span></span>

- <span data-ttu-id="8b1f4-140">Capacidad flexible; escalado o reducción vertical en función de las necesidades reales.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-140">Flexible capacity; scale up or down based on actual needs.</span></span>

<span data-ttu-id="8b1f4-141">La compilación de aplicaciones web con ASP.NET Core, hospedadas en Azure, ofrece muchas ventajas competitivas con respecto a las alternativas tradicionales.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-141">Building web applications with ASP.NET Core, hosted in Azure, offers many competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="8b1f4-142">Se ha optimizado ASP.NET Core para escenarios de hospedaje en la nube y prácticas de desarrollo de aplicaciones web modernas.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-142">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="8b1f4-143">En esta guía se ofrece información sobre cómo diseñar aplicaciones con ASP.NET Core para sacar el máximo provecho de estas funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-143">In this guide, you'll learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="purpose"></a><span data-ttu-id="8b1f4-144">Propósito</span><span class="sxs-lookup"><span data-stu-id="8b1f4-144">Purpose</span></span>

<span data-ttu-id="8b1f4-145">En esta guía se proporcionan instrucciones integrales sobre cómo compilar aplicaciones web *monolíticas* con ASP.NET Core y Azure.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-145">This guide provides end-to-end guidance on building *monolithic* web applications using ASP.NET Core and Azure.</span></span> <span data-ttu-id="8b1f4-146">En este contexto, "monolíticas" hace referencia al hecho de que estas aplicaciones se implementan como una sola unidad, no como una colección de aplicaciones y servicios que interactúan.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-146">In this context, "monolithic" refers to the fact that these applications are deployed as a single unit, not as a collection of interacting services and applications.</span></span>

<span data-ttu-id="8b1f4-147">Esta guía complementa los microservicios de .NET ["_. Arquitectura para aplicaciones .NET en contenedor_"](../microservices-architecture/index.md) más centrada en Docker, los microservicios y la implementación de contenedores para hospedar aplicaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-147">This guide is complementary to the ["_.NET Microservices. Architecture for Containerized .NET Applications_"](../microservices-architecture/index.md) which focuses more on Docker, Microservices, and Deployment of Containers to host enterprise applications.</span></span>

### <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="8b1f4-148">Microservicios de .NET.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-148">.NET Microservices.</span></span> <span data-ttu-id="8b1f4-149">Arquitectura para aplicaciones .NET en contenedor</span><span class="sxs-lookup"><span data-stu-id="8b1f4-149">Architecture for Containerized .NET Applications</span></span>

- <span data-ttu-id="8b1f4-150">**Libro electrónico**</span><span class="sxs-lookup"><span data-stu-id="8b1f4-150">**e-book**</span></span>  
  <https://aka.ms/MicroservicesEbook>
- <span data-ttu-id="8b1f4-151">**Aplicación de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="8b1f4-151">**Sample Application**</span></span>  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="8b1f4-152">Destinatarios de esta guía</span><span class="sxs-lookup"><span data-stu-id="8b1f4-152">Who should use this guide</span></span>

<span data-ttu-id="8b1f4-153">Los destinatarios de esta guía son principalmente desarrolladores, jefes de desarrollo y arquitectos interesados en crear aplicaciones web modernas con tecnologías y servicios de Microsoft en la nube.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-153">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="8b1f4-154">Otros destinatarios secundarios son los responsables de tomar decisiones técnicas que ya están familiarizados con ASP.NET o Azure y que buscan información sobre si tiene sentido actualizar a ASP.NET Core para los proyectos nuevos o existentes.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-154">A secondary audience is technical decision makers who are already familiar ASP.NET or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="8b1f4-155">Cómo leer esta guía</span><span class="sxs-lookup"><span data-stu-id="8b1f4-155">How you can use this guide</span></span>

<span data-ttu-id="8b1f4-156">Esta guía se ha comprimido en un documento relativamente pequeño que se centra en la creación de aplicaciones web con modernas tecnologías de .NET y Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-156">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Windows Azure.</span></span> <span data-ttu-id="8b1f4-157">Por lo tanto, se puede leer completa para proporcionar una base de conocimiento sobre estas aplicaciones y sus consideraciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-157">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="8b1f4-158">La guía, junto con su aplicación de ejemplo, también puede servir como punto inicial o referencia.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-158">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="8b1f4-159">Use la aplicación de ejemplo asociada como una plantilla para las aplicaciones propias o para consultar cómo se pueden organizar los componentes de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-159">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="8b1f4-160">Consulte los principios y la cobertura de la arquitectura, las opciones tecnológicas y las consideraciones para la toma de decisiones de esta guía a la hora de sopesar estas opciones para su propia aplicación.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-160">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when you're weighing these choices for your own application.</span></span>

<span data-ttu-id="8b1f4-161">No dude en reenviar esta guía a su equipo para ayudarlo a garantizar una comprensión común de estas consideraciones y oportunidades.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-161">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="8b1f4-162">El hecho de que todos los usuarios trabajen a partir de un conjunto común de principios subyacentes y terminología permite garantizar una aplicación coherente de las prácticas y los patrones de diseño.</span><span class="sxs-lookup"><span data-stu-id="8b1f4-162">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="8b1f4-163">Referencias</span><span class="sxs-lookup"><span data-stu-id="8b1f4-163">References</span></span>

- <span data-ttu-id="8b1f4-164">**Selección entre .NET Core y .NET Framework para aplicaciones de servidor**</span><span class="sxs-lookup"><span data-stu-id="8b1f4-164">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  [https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server](../choosing-core-framework-server.md)

>[!div class="step-by-step"]
>[<span data-ttu-id="8b1f4-165">Siguiente</span><span class="sxs-lookup"><span data-stu-id="8b1f4-165">Next</span></span>](modern-web-applications-characteristics.md)