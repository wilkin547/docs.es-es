---
title: Microservicios de .NET. Arquitectura para aplicaciones .NET en contenedor
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Los microservicios son servicios modulares que se pueden implementar de forma independiente. Los contenedores de Docker (para Linux y Windows) simplifican la implementación y las pruebas mediante la unión de un servicio y sus dependencias en una sola unidad que, después, se ejecuta en un entorno aislado.
ms.date: 09/02/2020
ms.openlocfilehash: aea5012fee102f388827d146043e69592e14f22b
ms.sourcegitcommit: b78018c850590dfc0348301e1748b779c28604cc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "89379140"
---
# <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="180e6-105">Microservicios de .NET: Arquitectura para aplicaciones .NET en contenedor</span><span class="sxs-lookup"><span data-stu-id="180e6-105">.NET Microservices: Architecture for Containerized .NET Applications</span></span>

![Portada del libro](./media/cover-small.png)

<span data-ttu-id="180e6-107">**EDICIÓN v3.1.2**: actualizada a ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="180e6-107">**EDITION v3.1.2** - Updated to ASP.NET Core 3.1</span></span>

<span data-ttu-id="180e6-108">Esta guía es una introducción al desarrollo de aplicaciones basadas en microservicios y a su administración mediante contenedores.</span><span class="sxs-lookup"><span data-stu-id="180e6-108">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="180e6-109">En ella se trata el diseño de la arquitectura y los métodos de implementación con .NET Core y contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="180e6-109">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span>

<span data-ttu-id="180e6-110">Para que sea más fácil empezar a trabajar, la guía se centra en una aplicación de referencia en contenedor y basada en microservicios que puede explorar.</span><span class="sxs-lookup"><span data-stu-id="180e6-110">To make it easier to get started, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="180e6-111">La aplicación de referencia está disponible en el repositorio de GitHub [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="180e6-111">The reference application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

## <a name="action-links"></a><span data-ttu-id="180e6-112">Vínculos de acción</span><span class="sxs-lookup"><span data-stu-id="180e6-112">Action links</span></span>

- <span data-ttu-id="180e6-113">Este libro electrónico también está disponible en formato PDF (solo versión en inglés) [Descargar](https://aka.ms/microservicesebook)</span><span class="sxs-lookup"><span data-stu-id="180e6-113">This e-book is also available in a PDF format (English version only) [Download](https://aka.ms/microservicesebook)</span></span>

- <span data-ttu-id="180e6-114">Clone o bifurque la aplicación de referencia [eShopOnContainers en GitHub](https://github.com/dotnet-architecture/eShopOnContainers)</span><span class="sxs-lookup"><span data-stu-id="180e6-114">Clone/Fork the reference application [eShopOnContainers on GitHub](https://github.com/dotnet-architecture/eShopOnContainers)</span></span>

- <span data-ttu-id="180e6-115">Vea el [vídeo de introducción en Channel 9](https://aka.ms/microservices-video)</span><span class="sxs-lookup"><span data-stu-id="180e6-115">Watch the [introductory video on Channel 9](https://aka.ms/microservices-video)</span></span>

- <span data-ttu-id="180e6-116">Conozca la [arquitectura de microservicios](https://aka.ms/MicroservicesArchitecture) inmediatamente</span><span class="sxs-lookup"><span data-stu-id="180e6-116">Get to know the [Microservices Architecture](https://aka.ms/MicroservicesArchitecture) right away</span></span>

## <a name="introduction"></a><span data-ttu-id="180e6-117">Introducción</span><span class="sxs-lookup"><span data-stu-id="180e6-117">Introduction</span></span>

<span data-ttu-id="180e6-118">Las empresas cada vez ahorran más costos, resuelven más problemas de implementación y mejoran más las operaciones de DevOps y producción mediante el uso de contenedores.</span><span class="sxs-lookup"><span data-stu-id="180e6-118">Enterprises are increasingly realizing cost savings, solving deployment problems, and improving DevOps and production operations by using containers.</span></span> <span data-ttu-id="180e6-119">Microsoft ha lanzado recientemente innovaciones en los contenedores de Windows y Linux con la creación de productos como Azure Kubernetes Service y Azure Service Fabric, contando además con la colaboración de líderes del sector como Docker, Mesosphere y Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="180e6-119">Microsoft has been releasing container innovations for Windows and Linux by creating products like Azure Kubernetes Service and Azure Service Fabric, and by partnering with industry leaders like Docker, Mesosphere, and Kubernetes.</span></span> <span data-ttu-id="180e6-120">Estos productos ofrecen soluciones de contenedores que ayudan a las empresas a compilar e implementar aplicaciones a velocidad y escala de nube, sea cual sea la plataforma o las herramientas que hayan elegido.</span><span class="sxs-lookup"><span data-stu-id="180e6-120">These products deliver container solutions that help companies build and deploy applications at cloud speed and scale, whatever their choice of platform or tools.</span></span>

<span data-ttu-id="180e6-121">Docker se está convirtiendo en el estándar de facto del sector de los contenedores, ya que es compatible con los proveedores más importantes del ecosistema de Windows y Linux.</span><span class="sxs-lookup"><span data-stu-id="180e6-121">Docker is becoming the de facto standard in the container industry, supported by the most significant vendors in the Windows and Linux ecosystems.</span></span> <span data-ttu-id="180e6-122">(Microsoft es uno de los principales proveedores de nube que admite Docker). En el futuro, Docker probablemente estará omnipresente en todos los centros de datos en la nube o locales.</span><span class="sxs-lookup"><span data-stu-id="180e6-122">(Microsoft is one of the main cloud vendors supporting Docker.) In the future, Docker will probably be ubiquitous in any datacenter in the cloud or on-premises.</span></span>

<span data-ttu-id="180e6-123">Además, la arquitectura de [microservicios](https://martinfowler.com/articles/microservices.html) se está convirtiendo en un enfoque fundamental para las aplicaciones críticas distribuidas.</span><span class="sxs-lookup"><span data-stu-id="180e6-123">In addition, the [microservices](https://martinfowler.com/articles/microservices.html) architecture is emerging as an important approach for distributed mission-critical applications.</span></span> <span data-ttu-id="180e6-124">En una arquitectura basada en microservicios, la aplicación se basa en una colección de servicios que se pueden desarrollar, probar, implementar y versionar por separado.</span><span class="sxs-lookup"><span data-stu-id="180e6-124">In a microservice-based architecture, the application is built on a collection of services that can be developed, tested, deployed, and versioned independently.</span></span>

## <a name="about-this-guide"></a><span data-ttu-id="180e6-125">Acerca de esta guía</span><span class="sxs-lookup"><span data-stu-id="180e6-125">About this guide</span></span>

<span data-ttu-id="180e6-126">Esta guía es una introducción al desarrollo de aplicaciones basadas en microservicios y a su administración mediante contenedores.</span><span class="sxs-lookup"><span data-stu-id="180e6-126">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="180e6-127">En ella se trata el diseño de la arquitectura y los métodos de implementación con .NET Core y contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="180e6-127">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span> <span data-ttu-id="180e6-128">Para que sea más fácil empezar a trabajar con contenedores y microservicios, la guía se centra en una aplicación de referencia en contenedor y basada en microservicios que puede explorar.</span><span class="sxs-lookup"><span data-stu-id="180e6-128">To make it easier to get started with containers and microservices, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="180e6-129">Esta misma aplicación de ejemplo está disponible en el repositorio de GitHub [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="180e6-129">The sample application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

<span data-ttu-id="180e6-130">Esta guía incluye el desarrollo fundamental y una guía de arquitectura principalmente en el nivel del entorno de desarrollo con especial hincapié en dos tecnologías: Docker y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="180e6-130">This guide provides foundational development and architectural guidance primarily at a development environment level with a focus on two technologies: Docker and .NET Core.</span></span> <span data-ttu-id="180e6-131">Nuestra intención es que lea esta guía cuando reflexione sobre el diseño de las aplicaciones sin centrarse en la infraestructura (en la nube o local) de su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="180e6-131">Our intention is that you read this guide when thinking about your application design without focusing on the infrastructure (cloud or on-premises) of your production environment.</span></span> <span data-ttu-id="180e6-132">Tomará decisiones sobre la infraestructura más adelante, cuando cree aplicaciones listas para la producción.</span><span class="sxs-lookup"><span data-stu-id="180e6-132">You will make decisions about your infrastructure later, when you create your production-ready applications.</span></span> <span data-ttu-id="180e6-133">Por lo tanto, esta guía está diseñada para ser independiente de la infraestructura y centrarse en el desarrollo y el entorno.</span><span class="sxs-lookup"><span data-stu-id="180e6-133">Therefore, this guide is intended to be infrastructure agnostic and more development-environment-centric.</span></span>

<span data-ttu-id="180e6-134">Una vez que haya estudiado esta guía, el siguiente paso que debería dar es obtener información sobre los microservicios listos para la producción en Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="180e6-134">After you have studied this guide, your next step would be to learn about production-ready microservices on Microsoft Azure.</span></span>

## <a name="version"></a><span data-ttu-id="180e6-135">Versión</span><span class="sxs-lookup"><span data-stu-id="180e6-135">Version</span></span>

<span data-ttu-id="180e6-136">Esta guía se ha revisado para abarcar la versión **.NET Core 3.1** junto con muchas actualizaciones adicionales relacionadas con la misma "ola" de tecnologías (es decir, Azure y otras tecnologías de terceros) que coincidan en el tiempo con la versión de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="180e6-136">This guide has been revised to cover **.NET Core 3.1** version along with many additional updates related to the same “wave” of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET Core 3.1 release.</span></span> <span data-ttu-id="180e6-137">Este es el motivo por el que la versión del libro se ha actualizado también a la versión **3.1**.</span><span class="sxs-lookup"><span data-stu-id="180e6-137">That’s why the book version has also been updated to version **3.1**.</span></span>

## <a name="what-this-guide-does-not-cover"></a><span data-ttu-id="180e6-138">Aspectos no tratados en esta guía</span><span class="sxs-lookup"><span data-stu-id="180e6-138">What this guide does not cover</span></span>

<span data-ttu-id="180e6-139">Esta guía no se centra en el ciclo de vida de la aplicación, DevOps, las canalizaciones CI/CD ni el trabajo de equipo.</span><span class="sxs-lookup"><span data-stu-id="180e6-139">This guide does not focus on the application lifecycle, DevOps, CI/CD pipelines, or team work.</span></span> <span data-ttu-id="180e6-140">La guía complementaria [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) (Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y herramientas de Microsoft) se centra en esas cuestiones.</span><span class="sxs-lookup"><span data-stu-id="180e6-140">The complementary guide [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) focuses on that subject.</span></span> <span data-ttu-id="180e6-141">La guía actual tampoco proporciona detalles de implementación de la infraestructura de Azure, como información sobre orquestadores específicos.</span><span class="sxs-lookup"><span data-stu-id="180e6-141">The current guide also does not provide implementation details on Azure infrastructure, such as information on specific orchestrators.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="180e6-142">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="180e6-142">Additional resources</span></span>

- <span data-ttu-id="180e6-143">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft; libro electrónico descargable)</span><span class="sxs-lookup"><span data-stu-id="180e6-143">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book)</span></span>  
    <https://aka.ms/dockerlifecycleebook>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="180e6-144">Destinatarios de esta guía</span><span class="sxs-lookup"><span data-stu-id="180e6-144">Who should use this guide</span></span>

<span data-ttu-id="180e6-145">Esta guía se ha escrito para desarrolladores y arquitectos de soluciones que no están familiarizados con el desarrollo de aplicaciones basado en Docker y la arquitectura basada en microservicios.</span><span class="sxs-lookup"><span data-stu-id="180e6-145">We wrote this guide for developers and solution architects who are new to Docker-based application development and to microservices-based architecture.</span></span> <span data-ttu-id="180e6-146">Esta guía será de su interés si quiere obtener información sobre cómo crear arquitecturas, diseñar e implementar aplicaciones de prueba de concepto con tecnologías de desarrollo de Microsoft (con un hincapié especial en .NET Core) y con contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="180e6-146">This guide is for you if you want to learn how to architect, design, and implement proof-of-concept applications with Microsoft development technologies (with special focus on .NET Core) and with Docker containers.</span></span>

<span data-ttu-id="180e6-147">También le resultará útil si es el responsable de tomar decisiones técnicas (por ejemplo, un arquitecto empresarial) y necesita una descripción de la arquitectura y la tecnología antes de decidir qué enfoque tomar para el diseño de aplicaciones distribuidas tanto nuevas como modernas.</span><span class="sxs-lookup"><span data-stu-id="180e6-147">You will also find this guide useful if you are a technical decision maker, such as an enterprise architect, who wants an architecture and technology overview before you decide on what approach to select for new and modern distributed applications.</span></span>

### <a name="how-to-use-this-guide"></a><span data-ttu-id="180e6-148">Cómo usar esta guía</span><span class="sxs-lookup"><span data-stu-id="180e6-148">How to use this guide</span></span>

<span data-ttu-id="180e6-149">La primera parte de esta guía presenta los contenedores de Docker, describe cómo elegir entre .NET Core y .NET Framework como marco de desarrollo y proporciona una visión general de los microservicios.</span><span class="sxs-lookup"><span data-stu-id="180e6-149">The first part of this guide introduces Docker containers, discusses how to choose between .NET Core and the .NET Framework as a development framework, and provides an overview of microservices.</span></span> <span data-ttu-id="180e6-150">Este contenido está destinado a arquitectos y responsables de la toma de decisiones técnicas que quieren obtener información general pero que no necesitan centrarse en los detalles de la implementación de código.</span><span class="sxs-lookup"><span data-stu-id="180e6-150">This content is for architects and technical decision makers who want an overview but don't need to focus on code implementation details.</span></span>

<span data-ttu-id="180e6-151">La segunda parte de la guía comienza con la sección [Proceso de desarrollo de aplicaciones basadas en Docker](./docker-application-development-process/index.md).</span><span class="sxs-lookup"><span data-stu-id="180e6-151">The second part of the guide starts with the [Development process for Docker based applications](./docker-application-development-process/index.md) section.</span></span> <span data-ttu-id="180e6-152">Se centra en los patrones de desarrollo y microservicios empleados en la implementación de aplicaciones que usan .NET Core y Docker.</span><span class="sxs-lookup"><span data-stu-id="180e6-152">It focuses on the development and microservice patterns for implementing applications using .NET Core and Docker.</span></span> <span data-ttu-id="180e6-153">Esta sección será de gran interés para los desarrolladores y los arquitectos que quieran centrarse en el código, en los patrones y los detalles de implementación.</span><span class="sxs-lookup"><span data-stu-id="180e6-153">This section will be of most interest to developers and architects who want to focus on code and on patterns and implementation details.</span></span>

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a><span data-ttu-id="180e6-154">Aplicación de referencia relacionada de microservicios y basada en contenedor: eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="180e6-154">Related microservice and container-based reference application: eShopOnContainers</span></span>

<span data-ttu-id="180e6-155">La aplicación eShopOnContainers es una aplicación de referencia de código abierto para .NET Core y microservicios que está diseñada para implementarse mediante contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="180e6-155">The eShopOnContainers application is an open-source reference app for .NET Core and microservices that is designed to be deployed using Docker containers.</span></span> <span data-ttu-id="180e6-156">La aplicación consta de varios subsistemas, incluidos varios front-end de interfaz de usuario de almacén electrónico (una aplicación web de MVC, una SPA web y una aplicación móvil nativa).</span><span class="sxs-lookup"><span data-stu-id="180e6-156">The application consists of multiple subsystems, including several e-store UI front-ends (a Web MVC app, a Web SPA, and a native mobile app).</span></span> <span data-ttu-id="180e6-157">También incluye microservicios y contenedores de back-end para todas las operaciones del lado servidor necesarias.</span><span class="sxs-lookup"><span data-stu-id="180e6-157">It also includes the back-end microservices and containers for all required server-side operations.</span></span>

<span data-ttu-id="180e6-158">El propósito de la aplicación es presentar patrones arquitectónicos.</span><span class="sxs-lookup"><span data-stu-id="180e6-158">The purpose of the application is to showcase architectural patterns.</span></span> <span data-ttu-id="180e6-159">**NO SE TRATA DE UNA PLANTILLA LISTA PARA PRODUCCIÓN** para iniciar aplicaciones del mundo real.</span><span class="sxs-lookup"><span data-stu-id="180e6-159">**IT IS NOT A PRODUCTION-READY TEMPLATE** to start real-world applications.</span></span> <span data-ttu-id="180e6-160">De hecho, la aplicación se encuentra en un estado beta permanente, ya que también se usa para probar nuevas tecnologías potencialmente interesantes a medida que aparecen.</span><span class="sxs-lookup"><span data-stu-id="180e6-160">In fact, the application is in a permanent beta state, as it's also used to test new potentially interesting technologies as they show up.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="180e6-161">Envíenos sus comentarios.</span><span class="sxs-lookup"><span data-stu-id="180e6-161">Send us your feedback!</span></span>

<span data-ttu-id="180e6-162">Hemos creado esta guía para ayudarle a entender la arquitectura de aplicaciones y microservicios en contenedor en .NET.</span><span class="sxs-lookup"><span data-stu-id="180e6-162">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="180e6-163">La guía y la aplicación de referencia relacionada irán evolucionando, por lo que le agradecemos sus comentarios.</span><span class="sxs-lookup"><span data-stu-id="180e6-163">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="180e6-164">Si tiene comentarios sobre cómo se puede mejorar esta guía, envíelos a <https://aka.ms/ebookfeedback>.</span><span class="sxs-lookup"><span data-stu-id="180e6-164">If you have comments about how this guide can be improved, submit feedback at <https://aka.ms/ebookfeedback>.</span></span>

## <a name="credits"></a><span data-ttu-id="180e6-165">Créditos</span><span class="sxs-lookup"><span data-stu-id="180e6-165">Credits</span></span>

<span data-ttu-id="180e6-166">Coautores:</span><span class="sxs-lookup"><span data-stu-id="180e6-166">Co-Authors:</span></span>

> <span data-ttu-id="180e6-167">**Cesar de la Torre**, administrador de programas sénior del equipo de producto de .NET, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="180e6-167">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>
>
> <span data-ttu-id="180e6-168">**Bill Wagner**, desarrollador de contenido sénior de C+E, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="180e6-168">**Bill Wagner**, Sr. Content Developer, C+E, Microsoft Corp.</span></span>
>
> <span data-ttu-id="180e6-169">**Mike Rousos**, ingeniero de software principal del equipo de CAT de la división de desarrollo, Microsoft</span><span class="sxs-lookup"><span data-stu-id="180e6-169">**Mike Rousos**, Principal Software Engineer, DevDiv CAT team, Microsoft</span></span>

<span data-ttu-id="180e6-170">Editores:</span><span class="sxs-lookup"><span data-stu-id="180e6-170">Editors:</span></span>

> <span data-ttu-id="180e6-171">**Mike Pope**</span><span class="sxs-lookup"><span data-stu-id="180e6-171">**Mike Pope**</span></span>
>
> <span data-ttu-id="180e6-172">**Steve Hoag**</span><span class="sxs-lookup"><span data-stu-id="180e6-172">**Steve Hoag**</span></span>

<span data-ttu-id="180e6-173">Participantes y revisores:</span><span class="sxs-lookup"><span data-stu-id="180e6-173">Participants and reviewers:</span></span>

> <span data-ttu-id="180e6-174">**Jeffrey Richter**, ingeniero de software asociado del equipo de Azure, Microsoft</span><span class="sxs-lookup"><span data-stu-id="180e6-174">**Jeffrey Richter**, Partner Software Eng, Azure team, Microsoft</span></span>
>
> <span data-ttu-id="180e6-175">**Jimmy Bogard**, arquitecto jefe de Headspring</span><span class="sxs-lookup"><span data-stu-id="180e6-175">**Jimmy Bogard**, Chief Architect at Headspring</span></span>
>
> <span data-ttu-id="180e6-176">**Udi Dahan**, fundador y director general de Particular Software</span><span class="sxs-lookup"><span data-stu-id="180e6-176">**Udi Dahan**, Founder & CEO, Particular Software</span></span>
>
> <span data-ttu-id="180e6-177">**Jimmy Nilsson**, cofundador y director general de Factor10</span><span class="sxs-lookup"><span data-stu-id="180e6-177">**Jimmy Nilsson**, Co-founder and CEO of Factor10</span></span>
>
> <span data-ttu-id="180e6-178">**Glenn Condron**, director de programas sénior del equipo de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="180e6-178">**Glenn Condron**, Sr. Program Manager, ASP.NET team</span></span>
>
> <span data-ttu-id="180e6-179">**Mark Fussell**, responsable principal de administración de programas del equipo de Azure Service Fabric, Microsoft</span><span class="sxs-lookup"><span data-stu-id="180e6-179">**Mark Fussell**, Principal PM Lead, Azure Service Fabric team, Microsoft</span></span>
>
> <span data-ttu-id="180e6-180">**Diego Vega**, responsable de administración de programas del equipo de Entity Framework, Microsoft</span><span class="sxs-lookup"><span data-stu-id="180e6-180">**Diego Vega**, PM Lead, Entity Framework team, Microsoft</span></span>
>
> <span data-ttu-id="180e6-181">**Barry Dorrans**, director de programas de seguridad sénior</span><span class="sxs-lookup"><span data-stu-id="180e6-181">**Barry Dorrans**, Sr. Security Program Manager</span></span>
>
> <span data-ttu-id="180e6-182">**Rowan Miller**, director de programas sénior, Microsoft</span><span class="sxs-lookup"><span data-stu-id="180e6-182">**Rowan Miller**, Sr. Program Manager, Microsoft</span></span>
>
> <span data-ttu-id="180e6-183">**Ankit Asthana**, director principal de administración de programas del equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="180e6-183">**Ankit Asthana**, Principal PM Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="180e6-184">**Scott Hunter**, director asociado de administración de programas del equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="180e6-184">**Scott Hunter**, Partner Director PM, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="180e6-185">**Nish Anil**, director de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="180e6-185">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="180e6-186">**Dylan Reisenberger**, arquitecto y responsable de desarrollo de Polly</span><span class="sxs-lookup"><span data-stu-id="180e6-186">**Dylan Reisenberger**, Architect and Dev Lead at Polly</span></span>
>
> <span data-ttu-id="180e6-187">**Steve "ardalis" Smith**: instructor y arquitecto de software de [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="180e6-187">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>
>
> <span data-ttu-id="180e6-188">**Cooper Ian**, arquitecto de codificación de Brighter</span><span class="sxs-lookup"><span data-stu-id="180e6-188">**Ian Cooper**, Coding Architect at Brighter</span></span>
>
> <span data-ttu-id="180e6-189">**Unai Zorrilla**, arquitecto y responsable de desarrollo de Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="180e6-189">**Unai Zorrilla**, Architect and Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="180e6-190">**Eduard Tomas**, responsable de desarrollo de Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="180e6-190">**Eduard Tomas**, Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="180e6-191">**Ramon Tomas**, desarrollador de Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="180e6-191">**Ramon Tomas**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="180e6-192">**David Sanz**, desarrollador de Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="180e6-192">**David Sanz**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="180e6-193">**Javier Valero**, director de operaciones de Grupo Solutio</span><span class="sxs-lookup"><span data-stu-id="180e6-193">**Javier Valero**, Chief Operating Officer at Grupo Solutio</span></span>
>
> <span data-ttu-id="180e6-194">**Pierre Millet**, consultor sénior, Microsoft</span><span class="sxs-lookup"><span data-stu-id="180e6-194">**Pierre Millet**, Sr. Consultant, Microsoft</span></span>
>
> <span data-ttu-id="180e6-195">**Michael Friis**, administrador de productos de Docker Inc.</span><span class="sxs-lookup"><span data-stu-id="180e6-195">**Michael Friis**, Product Manager, Docker Inc</span></span>
>
> <span data-ttu-id="180e6-196">**Charles Lowell**, ingeniero de software del equipo de CAT de VS, Microsoft</span><span class="sxs-lookup"><span data-stu-id="180e6-196">**Charles Lowell**, Software Engineer, VS CAT team, Microsoft</span></span>
>
> <span data-ttu-id="180e6-197">**Miguel Veloso**, ingeniero de desarrollo de software en Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="180e6-197">**Miguel Veloso**, Software Development Engineer at Plain Concepts</span></span>
>
> <span data-ttu-id="180e6-198">**Sumit Ghosh**, asesor principal en Neudesic</span><span class="sxs-lookup"><span data-stu-id="180e6-198">**Sumit Ghosh**, Principal Consultant at Neudesic</span></span>

## <a name="copyright"></a><span data-ttu-id="180e6-199">Copyright</span><span class="sxs-lookup"><span data-stu-id="180e6-199">Copyright</span></span>

<span data-ttu-id="180e6-200">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="180e6-200">PUBLISHED BY</span></span>

<span data-ttu-id="180e6-201">Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio</span><span class="sxs-lookup"><span data-stu-id="180e6-201">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="180e6-202">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="180e6-202">A division of Microsoft Corporation</span></span>

<span data-ttu-id="180e6-203">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="180e6-203">One Microsoft Way</span></span>

<span data-ttu-id="180e6-204">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="180e6-204">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="180e6-205">Copyright © 2020 de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="180e6-205">Copyright © 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="180e6-206">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="180e6-206">All rights reserved.</span></span> <span data-ttu-id="180e6-207">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="180e6-207">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="180e6-208">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="180e6-208">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="180e6-209">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="180e6-209">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="180e6-210">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="180e6-210">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="180e6-211">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="180e6-211">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="180e6-212">Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="180e6-212">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="180e6-213">Mac y macOS son marcas comerciales de Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="180e6-213">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="180e6-214">El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.</span><span class="sxs-lookup"><span data-stu-id="180e6-214">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="180e6-215">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="180e6-215">All other marks and logos are property of their respective owners.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="180e6-216">Siguiente</span><span class="sxs-lookup"><span data-stu-id="180e6-216">Next</span></span>](container-docker-introduction/index.md)
