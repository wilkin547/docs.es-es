---
title: Microservicios de .NET. Arquitectura para aplicaciones .NET en contenedor
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Preliminares
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: d4499384d63f11a1d78d0aa84749aed8ea554794
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
![](./media/cover.png)

# <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="023d5-104">Microservicios de .NET.</span><span class="sxs-lookup"><span data-stu-id="023d5-104">.NET Microservices.</span></span> <span data-ttu-id="023d5-105">Arquitectura para aplicaciones .NET en contenedor</span><span class="sxs-lookup"><span data-stu-id="023d5-105">Architecture for Containerized .NET Applications</span></span>

<span data-ttu-id="023d5-106">DESCARGA disponible en: <https://aka.ms/microservicesebook></span><span class="sxs-lookup"><span data-stu-id="023d5-106">DOWNLOAD available at: <https://aka.ms/microservicesebook></span></span>

<span data-ttu-id="023d5-107">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="023d5-107">PUBLISHED BY</span></span>

<span data-ttu-id="023d5-108">Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio</span><span class="sxs-lookup"><span data-stu-id="023d5-108">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="023d5-109">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="023d5-109">A division of Microsoft Corporation</span></span>

<span data-ttu-id="023d5-110">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="023d5-110">One Microsoft Way</span></span>

<span data-ttu-id="023d5-111">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="023d5-111">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="023d5-112">Copyright © 2017 de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="023d5-112">Copyright © 2017 by Microsoft Corporation</span></span>

<span data-ttu-id="023d5-113">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="023d5-113">All rights reserved.</span></span> <span data-ttu-id="023d5-114">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="023d5-114">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="023d5-115">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="023d5-115">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="023d5-116">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="023d5-116">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="023d5-117">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="023d5-117">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="023d5-118">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="023d5-118">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="023d5-119">Microsoft y las marcas comerciales indicadas en http://www.microsoft.com en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="023d5-119">Microsoft and the trademarks listed at http://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="023d5-120">Mac y macOS son marcas comerciales de Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="023d5-120">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="023d5-121">El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.</span><span class="sxs-lookup"><span data-stu-id="023d5-121">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="023d5-122">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="023d5-122">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="023d5-123">Coautores:</span><span class="sxs-lookup"><span data-stu-id="023d5-123">Co-Authors:</span></span>

> <span data-ttu-id="023d5-124">**Cesar de la Torre**, administrador de programas sénior del equipo del producto de .NET, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="023d5-124">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>
>
> <span data-ttu-id="023d5-125">**Bill Wagner**, desarrollador de contenido sénior de C+E, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="023d5-125">**Bill Wagner**, Sr. Content Developer, C+E, Microsoft Corp.</span></span>
>
> <span data-ttu-id="023d5-126">**Mike Rousos**, ingeniero de software principal del equipo de CAT de la división de desarrollo, Microsoft</span><span class="sxs-lookup"><span data-stu-id="023d5-126">**Mike Rousos**, Principal Software Engineer, DevDiv CAT team, Microsoft</span></span>

<span data-ttu-id="023d5-127">Editores:</span><span class="sxs-lookup"><span data-stu-id="023d5-127">Editors:</span></span>

> <span data-ttu-id="023d5-128">**Mike Pope**</span><span class="sxs-lookup"><span data-stu-id="023d5-128">**Mike Pope**</span></span>
>
> <span data-ttu-id="023d5-129">**Steve Hoag**</span><span class="sxs-lookup"><span data-stu-id="023d5-129">**Steve Hoag**</span></span>

<span data-ttu-id="023d5-130">Participantes y revisores:</span><span class="sxs-lookup"><span data-stu-id="023d5-130">Participants and reviewers:</span></span>

> <span data-ttu-id="023d5-131">**Jeffrey Richter**, ingeniero de software asociado del equipo de Azure, Microsoft</span><span class="sxs-lookup"><span data-stu-id="023d5-131">**Jeffrey Richter**, Partner Software Eng, Azure team, Microsoft</span></span>
>
> <span data-ttu-id="023d5-132">**Jimmy Bogard**, arquitecto jefe de Headspring</span><span class="sxs-lookup"><span data-stu-id="023d5-132">**Jimmy Bogard**, Chief Architect at Headspring</span></span>
>
> <span data-ttu-id="023d5-133">**Udi Dahan**, fundador y director general de Particular Software</span><span class="sxs-lookup"><span data-stu-id="023d5-133">**Udi Dahan**, Founder & CEO, Particular Software</span></span>
>
> <span data-ttu-id="023d5-134">**Jimmy Nilsson**, cofundador y director general de Factor10</span><span class="sxs-lookup"><span data-stu-id="023d5-134">**Jimmy Nilsson**, Co-founder and CEO of Factor10</span></span>
>
> <span data-ttu-id="023d5-135">**Glenn Condron**, director de programas sénior del equipo de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="023d5-135">**Glenn Condron**, Sr. Program Manager, ASP.NET team</span></span>
>
> <span data-ttu-id="023d5-136">**Mark Fussell**, responsable principal de administración de programas del equipo de Azure Service Fabric, Microsoft</span><span class="sxs-lookup"><span data-stu-id="023d5-136">**Mark Fussell**, Principal PM Lead, Azure Service Fabric team, Microsoft</span></span>
>
> <span data-ttu-id="023d5-137">**Diego Vega**, responsable de administración de programas del equipo de Entity Framework, Microsoft</span><span class="sxs-lookup"><span data-stu-id="023d5-137">**Diego Vega**, PM Lead, Entity Framework team, Microsoft</span></span>
>
> <span data-ttu-id="023d5-138">**Barry Dorrans**, administrador de programas de seguridad sénior</span><span class="sxs-lookup"><span data-stu-id="023d5-138">**Barry Dorrans**, Sr. Security Program Manager</span></span>
>
> <span data-ttu-id="023d5-139">**Rowan Miller**, administrador de programas sénior, Microsoft</span><span class="sxs-lookup"><span data-stu-id="023d5-139">**Rowan Miller**, Sr. Program Manager, Microsoft</span></span>
>
> <span data-ttu-id="023d5-140">**Ankit Asthana**, director principal de administración de programas del equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="023d5-140">**Ankit Asthana**, Principal PM Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="023d5-141">**Scott Hunter**, director asociado de administración de programas del equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="023d5-141">**Scott Hunter**, Partner Director PM, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="023d5-142">**Dylan Reisenberger**, arquitecto y responsable de desarrollo de Polly</span><span class="sxs-lookup"><span data-stu-id="023d5-142">**Dylan Reisenberger**, Architect and Dev Lead at Polly</span></span>
>
> <span data-ttu-id="023d5-143">**Steve Smith**, artesano e instructor de software de ASPSmith Ltd.</span><span class="sxs-lookup"><span data-stu-id="023d5-143">**Steve Smith**, Software Craftsman & Trainer at ASPSmith Ltd.</span></span>
>
> <span data-ttu-id="023d5-144">**Cooper Ian**, arquitecto de codificación de Brighter</span><span class="sxs-lookup"><span data-stu-id="023d5-144">**Ian Cooper**, Coding Architect at Brighter</span></span>
>
> <span data-ttu-id="023d5-145">**Unai Zorrilla**, arquitecto y responsable de desarrollo de Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="023d5-145">**Unai Zorrilla**, Architect and Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="023d5-146">**Eduard Tomas**, responsable de desarrollo de Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="023d5-146">**Eduard Tomas**, Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="023d5-147">**Ramon Tomas**, desarrollador de Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="023d5-147">**Ramon Tomas**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="023d5-148">**David Sanz**, desarrollador de Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="023d5-148">**David Sanz**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="023d5-149">**Javier Valero**, director de operaciones de Grupo Solutio</span><span class="sxs-lookup"><span data-stu-id="023d5-149">**Javier Valero**, Chief Operating Officer at Grupo Solutio</span></span>
>
> <span data-ttu-id="023d5-150">**Pierre Millet**, asesor sénior de Microsoft</span><span class="sxs-lookup"><span data-stu-id="023d5-150">**Pierre Millet**, Sr. Consultant, Microsoft</span></span>
>
> <span data-ttu-id="023d5-151">**Michael Friis**, administrador de productos de Docker Inc.</span><span class="sxs-lookup"><span data-stu-id="023d5-151">**Michael Friis**, Product Manager, Docker Inc</span></span>
>
> <span data-ttu-id="023d5-152">**Charles Lowell**, ingeniero de software del equipo de CAT de VS, Microsoft</span><span class="sxs-lookup"><span data-stu-id="023d5-152">**Charles Lowell**, Software Engineer, VS CAT team, Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="023d5-153">Introducción</span><span class="sxs-lookup"><span data-stu-id="023d5-153">Introduction</span></span>

<span data-ttu-id="023d5-154">Las empresas cada vez ahorran más costos, resuelven más problemas de implementación y mejoran más las operaciones de DevOps y producción mediante el uso de contenedores.</span><span class="sxs-lookup"><span data-stu-id="023d5-154">Enterprises are increasingly realizing cost savings, solving deployment problems, and improving DevOps and production operations by using containers.</span></span> <span data-ttu-id="023d5-155">Microsoft ha lanzado recientemente innovaciones en los contenedores de Windows y Linux con la creación de productos como Azure Container Service y Azure Service Fabric, contando además con la colaboración de líderes del sector como Docker, Mesosphere y Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="023d5-155">Microsoft has been releasing container innovations for Windows and Linux by creating products like Azure Container Service and Azure Service Fabric, and by partnering with industry leaders like Docker, Mesosphere, and Kubernetes.</span></span> <span data-ttu-id="023d5-156">Estos productos ofrecen soluciones de contenedores que ayudan a las empresas a compilar e implementar aplicaciones a velocidad y escala de nube, sea cual sea la plataforma o las herramientas que hayan elegido.</span><span class="sxs-lookup"><span data-stu-id="023d5-156">These products deliver container solutions that help companies build and deploy applications at cloud speed and scale, whatever their choice of platform or tools.</span></span>

<span data-ttu-id="023d5-157">Docker se está convirtiendo en el estándar de facto del sector de los contenedores, ya que es compatible con los proveedores más importantes del ecosistema de Windows y Linux.</span><span class="sxs-lookup"><span data-stu-id="023d5-157">Docker is becoming the de facto standard in the container industry, supported by the most significant vendors in the Windows and Linux ecosystems.</span></span> <span data-ttu-id="023d5-158">(Microsoft es uno de los principales proveedores de nube que admite Docker). En el futuro, Docker probablemente estará omnipresente en todos los centros de datos en la nube o locales.</span><span class="sxs-lookup"><span data-stu-id="023d5-158">(Microsoft is one of the main cloud vendors supporting Docker.) In the future, Docker will probably be ubiquitous in any datacenter in the cloud or on-premises.</span></span>

<span data-ttu-id="023d5-159">Además, la arquitectura de [microservicios](https://martinfowler.com/articles/microservices.html) se está convirtiendo en un enfoque fundamental para las aplicaciones críticas distribuidas.</span><span class="sxs-lookup"><span data-stu-id="023d5-159">In addition, the [microservices](https://martinfowler.com/articles/microservices.html) architecture is emerging as an important approach for distributed mission-critical applications.</span></span> <span data-ttu-id="023d5-160">En una arquitectura basada en microservicios, la aplicación se basa en una colección de servicios que se pueden desarrollar, probar, implementar y versionar por separado.</span><span class="sxs-lookup"><span data-stu-id="023d5-160">In a microservice-based architecture, the application is built on a collection of services that can be developed, tested, deployed, and versioned independently.</span></span>

## <a name="about-this-guide"></a><span data-ttu-id="023d5-161">Acerca de esta guía</span><span class="sxs-lookup"><span data-stu-id="023d5-161">About this guide</span></span>

<span data-ttu-id="023d5-162">Esta guía es una introducción al desarrollo de aplicaciones basadas en microservicios y a su administración mediante contenedores.</span><span class="sxs-lookup"><span data-stu-id="023d5-162">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="023d5-163">En ella se trata el diseño de la arquitectura y los métodos de implementación con .NET Core y contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="023d5-163">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span> <span data-ttu-id="023d5-164">Para que sea más fácil empezar a trabajar con contenedores y microservicios, la guía se centra en una aplicación de referencia en contenedor y basada en microservicios que puede explorar.</span><span class="sxs-lookup"><span data-stu-id="023d5-164">To make it easier to get started with containers and microservices, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="023d5-165">Esta misma aplicación de ejemplo está disponible en el repositorio de GitHub [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="023d5-165">The sample application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

<span data-ttu-id="023d5-166">En esta guía se proporciona el desarrollo fundamental y una guía de arquitectura principalmente en el nivel del entorno de desarrollo con especial hincapié en dos tecnologías: Docker y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="023d5-166">This guide provides foundational development and architectural guidance primarily at a development environment level with a focus on two technologies: Docker and .NET Core.</span></span> <span data-ttu-id="023d5-167">Nuestra intención es que lea esta guía cuando reflexione sobre el diseño de las aplicaciones sin centrarse en la infraestructura (en la nube o local) de su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="023d5-167">Our intention is that you read this guide when thinking about your application design without focusing on the infrastructure (cloud or on-premises) of your production environment.</span></span> <span data-ttu-id="023d5-168">Tomará decisiones sobre la infraestructura más adelante, cuando cree aplicaciones listas para la producción.</span><span class="sxs-lookup"><span data-stu-id="023d5-168">You will make decisions about your infrastructure later, when you create your production-ready applications.</span></span> <span data-ttu-id="023d5-169">Por lo tanto, esta guía está diseñada para ser independiente de la infraestructura y centrarse en el desarrollo y el entorno.</span><span class="sxs-lookup"><span data-stu-id="023d5-169">Therefore, this guide is intended to be infrastructure agnostic and more development-environment-centric.</span></span>

<span data-ttu-id="023d5-170">Una vez que haya estudiado esta guía, el siguiente paso que debería dar es obtener información sobre los microservicios listos para la producción en Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="023d5-170">After you have studied this guide, your next step would be to learn about production-ready microservices on Microsoft Azure.</span></span>

## <a name="what-this-guide-does-not-cover"></a><span data-ttu-id="023d5-171">Aspectos no tratados en esta guía</span><span class="sxs-lookup"><span data-stu-id="023d5-171">What this guide does not cover</span></span>

<span data-ttu-id="023d5-172">Esta guía no se centra en el ciclo de vida de la aplicación, DevOps, las canalizaciones CI/CD ni el trabajo de equipo.</span><span class="sxs-lookup"><span data-stu-id="023d5-172">This guide does not focus on the application lifecycle, DevOps, CI/CD pipelines, or team work.</span></span> <span data-ttu-id="023d5-173">La guía complementaria [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) (Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y herramientas de Microsoft) se centra en esas cuestiones.</span><span class="sxs-lookup"><span data-stu-id="023d5-173">The complementary guide [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) focuses on that subject.</span></span> <span data-ttu-id="023d5-174">La guía actual tampoco proporciona detalles de implementación de la infraestructura de Azure, como información sobre orquestadores específicos.</span><span class="sxs-lookup"><span data-stu-id="023d5-174">The current guide also does not provide implementation details on Azure infrastructure, such as information on specific orchestrators.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="023d5-175">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="023d5-175">Additional resources</span></span>

-   <span data-ttu-id="023d5-176">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft; libro electrónico descargable) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span><span class="sxs-lookup"><span data-stu-id="023d5-176">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="023d5-177">Destinatarios de esta guía</span><span class="sxs-lookup"><span data-stu-id="023d5-177">Who should use this guide</span></span>

<span data-ttu-id="023d5-178">Esta guía se ha escrito para desarrolladores y arquitectos de soluciones que no están familiarizados con el desarrollo de aplicaciones basado en Docker y la arquitectura basada en microservicios.</span><span class="sxs-lookup"><span data-stu-id="023d5-178">We wrote this guide for developers and solution architects who are new to Docker-based application development and to microservices-based architecture.</span></span> <span data-ttu-id="023d5-179">Esta guía será de su interés si quiere obtener información sobre cómo crear arquitecturas, diseñar e implementar aplicaciones de prueba de concepto con tecnologías de desarrollo de Microsoft (con un hincapié especial en .NET Core) y con contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="023d5-179">This guide is for you if you want to learn how to architect, design, and implement proof-of-concept applications with Microsoft development technologies (with special focus on .NET Core) and with Docker containers.</span></span>

<span data-ttu-id="023d5-180">También le resultará útil si es el responsable de tomar decisiones técnicas (por ejemplo, un arquitecto empresarial) y necesita una descripción de la arquitectura y la tecnología antes de decidir qué enfoque tomar para el diseño de aplicaciones distribuidas tanto nuevas como modernas.</span><span class="sxs-lookup"><span data-stu-id="023d5-180">You will also find this guide useful if you are a technical decision maker, such as an enterprise architect, who wants an architecture and technology overview before you decide on what approach to select for new and modern distributed applications.</span></span>

### <a name="how-to-use-this-guide"></a><span data-ttu-id="023d5-181">Cómo usar esta guía</span><span class="sxs-lookup"><span data-stu-id="023d5-181">How to use this guide</span></span>

<span data-ttu-id="023d5-182">La primera parte de esta guía presenta los contenedores de Docker, describe cómo elegir entre .NET Core y .NET Framework como marco de desarrollo y proporciona una visión general de los microservicios.</span><span class="sxs-lookup"><span data-stu-id="023d5-182">The first part of this guide introduces Docker containers, discusses how to choose between .NET Core and the .NET Framework as a development framework, and provides an overview of microservices.</span></span> <span data-ttu-id="023d5-183">Este contenido está destinado a arquitectos y responsables de la toma de decisiones técnicas que quieren obtener información general pero que no necesitan centrarse en los detalles de la implementación de código.</span><span class="sxs-lookup"><span data-stu-id="023d5-183">This content is for architects and technical decision makers who want an overview but who do not need to focus on code implementation details.</span></span>

<span data-ttu-id="023d5-184">La segunda parte de la guía comienza con la sección [Proceso de desarrollo de aplicaciones basadas en Docker](#ch_dev_process_for_docker_based_apps).</span><span class="sxs-lookup"><span data-stu-id="023d5-184">The second part of the guide starts with the [Development process for Docker based applications](#ch_dev_process_for_docker_based_apps) section.</span></span> <span data-ttu-id="023d5-185">Se centra en los patrones de desarrollo y microservicios usados en la implementación de las aplicaciones que utilizan .NET Core y Docker.</span><span class="sxs-lookup"><span data-stu-id="023d5-185">It focuses on development and microservice patterns for implementing applications using .NET Core and Docker.</span></span> <span data-ttu-id="023d5-186">Esta sección será de gran interés para los desarrolladores y los arquitectos que quieran centrarse en el código, en los patrones y los detalles de implementación.</span><span class="sxs-lookup"><span data-stu-id="023d5-186">This section will be of most interest to developers and architects who want to focus on code and on patterns and implementation details.</span></span>

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a><span data-ttu-id="023d5-187">Aplicación de referencia relacionada de microservicios y basada en contenedor: eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="023d5-187">Related microservice and container-based reference application: eShopOnContainers</span></span>

<span data-ttu-id="023d5-188">La aplicación eShopOnContainers es una aplicación de referencia para .NET Core y microservicios que está diseñada para implementarse mediante contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="023d5-188">The eShopOnContainers application is a reference app for .NET Core and microservices that is designed to be deployed using Docker containers.</span></span> <span data-ttu-id="023d5-189">La aplicación consta de varios subsistemas, incluidos varios front-end de interfaz de usuario de almacén electrónico (una aplicación web y una aplicación móvil nativa).</span><span class="sxs-lookup"><span data-stu-id="023d5-189">The application consists of multiple subsystems, including several e-store UI front ends (a Web app and a native mobile app).</span></span> <span data-ttu-id="023d5-190">También incluye microservicios y contenedores de back-end para todas las operaciones del lado servidor necesarias.</span><span class="sxs-lookup"><span data-stu-id="023d5-190">It also includes the back-end microservices and containers for all required server-side operations.</span></span>

<span data-ttu-id="023d5-191">El código fuente de la aplicación de microservicios basada en contenedor es código abierto y está disponible en el repositorio de GitHub [eShopOnContainers](http://aka.ms/MicroservicesArchitecture).</span><span class="sxs-lookup"><span data-stu-id="023d5-191">This microservice and container-based application source code is open source and available at the [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) GitHub repo.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="023d5-192">Envíenos sus comentarios.</span><span class="sxs-lookup"><span data-stu-id="023d5-192">Send us your feedback!</span></span>

<span data-ttu-id="023d5-193">Hemos creado esta guía para ayudarle a entender la arquitectura de aplicaciones y microservicios en contenedor en .NET.</span><span class="sxs-lookup"><span data-stu-id="023d5-193">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="023d5-194">La guía y la aplicación de referencia relacionada irán evolucionando, por lo que le agradecemos sus comentarios.</span><span class="sxs-lookup"><span data-stu-id="023d5-194">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="023d5-195">Si tiene comentarios sobre cómo se puede mejorar esta guía, envíelos a:</span><span class="sxs-lookup"><span data-stu-id="023d5-195">If you have comments about how this guide can be improved, please send them to:</span></span>

[dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com)

>[!div class="step-by-step"]
<span data-ttu-id="023d5-196">[Siguiente] (container-docker-introduction/index.md)</span><span class="sxs-lookup"><span data-stu-id="023d5-196">[Next] (container-docker-introduction/index.md)</span></span>
