---
title: Microservicios de .NET. Arquitectura para aplicaciones .NET en contenedor
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Los microservicios son servicios modulares que se pueden implementar de forma independiente. Los contenedores de Docker (para Linux y Windows) simplifican la implementación y las pruebas mediante la unión de un servicio y sus dependencias en una sola unidad que, después, se ejecuta en un entorno aislado.
ms.date: 01/13/2021
ms.openlocfilehash: a9017d2e9acbcbb861a35f0187632dc90c52e171
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188379"
---
# <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="35ffb-105">Microservicios de .NET: Arquitectura para aplicaciones .NET en contenedor</span><span class="sxs-lookup"><span data-stu-id="35ffb-105">.NET Microservices: Architecture for Containerized .NET Applications</span></span>

![Portada del libro](./media/cover-small.png)

<span data-ttu-id="35ffb-107">**EDICIÓN v5.0**: actualizada a ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="35ffb-107">**EDITION v5.0** - Updated to ASP.NET Core 5.0</span></span>

<span data-ttu-id="35ffb-108">Consulte el [registro de cambios](https://aka.ms/MicroservicesEbookChangelog) para ver las modificaciones del libro y las colaboraciones para la comunidad.</span><span class="sxs-lookup"><span data-stu-id="35ffb-108">Refer [changelog](https://aka.ms/MicroservicesEbookChangelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="35ffb-109">Esta guía es una introducción al desarrollo de aplicaciones basadas en microservicios y a su administración mediante contenedores.</span><span class="sxs-lookup"><span data-stu-id="35ffb-109">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="35ffb-110">En ella se trata el diseño de la arquitectura y los métodos de implementación con .NET 5 y contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="35ffb-110">It discusses architectural design and implementation approaches using .NET and Docker containers.</span></span>

<span data-ttu-id="35ffb-111">Para que sea más fácil empezar a trabajar, la guía se centra en una aplicación de referencia en contenedor y basada en microservicios que puede explorar.</span><span class="sxs-lookup"><span data-stu-id="35ffb-111">To make it easier to get started, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="35ffb-112">La aplicación de referencia está disponible en el repositorio de GitHub [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="35ffb-112">The reference application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

## <a name="action-links"></a><span data-ttu-id="35ffb-113">Vínculos de acción</span><span class="sxs-lookup"><span data-stu-id="35ffb-113">Action links</span></span>

- <span data-ttu-id="35ffb-114">Este libro electrónico también está disponible en formato PDF (solo versión en inglés) [Descargar](https://aka.ms/microservicesebook)</span><span class="sxs-lookup"><span data-stu-id="35ffb-114">This e-book is also available in a PDF format (English version only) [Download](https://aka.ms/microservicesebook)</span></span>

- <span data-ttu-id="35ffb-115">Clone o bifurque la aplicación de referencia [eShopOnContainers en GitHub](https://github.com/dotnet-architecture/eShopOnContainers)</span><span class="sxs-lookup"><span data-stu-id="35ffb-115">Clone/Fork the reference application [eShopOnContainers on GitHub](https://github.com/dotnet-architecture/eShopOnContainers)</span></span>

- <span data-ttu-id="35ffb-116">Vea el [vídeo de introducción en Channel 9](https://aka.ms/microservices-video)</span><span class="sxs-lookup"><span data-stu-id="35ffb-116">Watch the [introductory video on Channel 9](https://aka.ms/microservices-video)</span></span>

- <span data-ttu-id="35ffb-117">Conozca la [arquitectura de microservicios](https://aka.ms/MicroservicesArchitecture) inmediatamente</span><span class="sxs-lookup"><span data-stu-id="35ffb-117">Get to know the [Microservices Architecture](https://aka.ms/MicroservicesArchitecture) right away</span></span>

## <a name="introduction"></a><span data-ttu-id="35ffb-118">Introducción</span><span class="sxs-lookup"><span data-stu-id="35ffb-118">Introduction</span></span>

<span data-ttu-id="35ffb-119">Las empresas cada vez ahorran más costos, resuelven más problemas de implementación y mejoran más las operaciones de DevOps y producción mediante el uso de contenedores.</span><span class="sxs-lookup"><span data-stu-id="35ffb-119">Enterprises are increasingly realizing cost savings, solving deployment problems, and improving DevOps and production operations by using containers.</span></span> <span data-ttu-id="35ffb-120">Microsoft ha lanzado recientemente innovaciones en los contenedores de Windows y Linux con la creación de productos como Azure Kubernetes Service y Azure Service Fabric, contando además con la colaboración de líderes del sector como Docker, Mesosphere y Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="35ffb-120">Microsoft has been releasing container innovations for Windows and Linux by creating products like Azure Kubernetes Service and Azure Service Fabric, and by partnering with industry leaders like Docker, Mesosphere, and Kubernetes.</span></span> <span data-ttu-id="35ffb-121">Estos productos ofrecen soluciones de contenedores que ayudan a las empresas a compilar e implementar aplicaciones a velocidad y escala de nube, sea cual sea la plataforma o las herramientas que hayan elegido.</span><span class="sxs-lookup"><span data-stu-id="35ffb-121">These products deliver container solutions that help companies build and deploy applications at cloud speed and scale, whatever their choice of platform or tools.</span></span>

<span data-ttu-id="35ffb-122">Docker se está convirtiendo en el estándar de facto del sector de los contenedores, ya que es compatible con los proveedores más importantes del ecosistema de Windows y Linux.</span><span class="sxs-lookup"><span data-stu-id="35ffb-122">Docker is becoming the de facto standard in the container industry, supported by the most significant vendors in the Windows and Linux ecosystems.</span></span> <span data-ttu-id="35ffb-123">(Microsoft es uno de los principales proveedores de nube que admite Docker). En el futuro, Docker probablemente estará omnipresente en todos los centros de datos en la nube o locales.</span><span class="sxs-lookup"><span data-stu-id="35ffb-123">(Microsoft is one of the main cloud vendors supporting Docker.) In the future, Docker will probably be ubiquitous in any datacenter in the cloud or on-premises.</span></span>

<span data-ttu-id="35ffb-124">Además, la arquitectura de [microservicios](https://martinfowler.com/articles/microservices.html) se está convirtiendo en un enfoque fundamental para las aplicaciones críticas distribuidas.</span><span class="sxs-lookup"><span data-stu-id="35ffb-124">In addition, the [microservices](https://martinfowler.com/articles/microservices.html) architecture is emerging as an important approach for distributed mission-critical applications.</span></span> <span data-ttu-id="35ffb-125">En una arquitectura basada en microservicios, la aplicación se basa en una colección de servicios que se pueden desarrollar, probar, implementar y versionar por separado.</span><span class="sxs-lookup"><span data-stu-id="35ffb-125">In a microservice-based architecture, the application is built on a collection of services that can be developed, tested, deployed, and versioned independently.</span></span>

## <a name="about-this-guide"></a><span data-ttu-id="35ffb-126">Acerca de esta guía</span><span class="sxs-lookup"><span data-stu-id="35ffb-126">About this guide</span></span>

<span data-ttu-id="35ffb-127">Esta guía es una introducción al desarrollo de aplicaciones basadas en microservicios y a su administración mediante contenedores.</span><span class="sxs-lookup"><span data-stu-id="35ffb-127">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="35ffb-128">En ella se trata el diseño de la arquitectura y los métodos de implementación con .NET 5 y contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="35ffb-128">It discusses architectural design and implementation approaches using .NET and Docker containers.</span></span> <span data-ttu-id="35ffb-129">Para que sea más fácil empezar a trabajar con contenedores y microservicios, la guía se centra en una aplicación de referencia en contenedor y basada en microservicios que puede explorar.</span><span class="sxs-lookup"><span data-stu-id="35ffb-129">To make it easier to get started with containers and microservices, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="35ffb-130">Esta misma aplicación de ejemplo está disponible en el repositorio de GitHub [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="35ffb-130">The sample application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

<span data-ttu-id="35ffb-131">Esta guía incluye el desarrollo fundamental y una guía de arquitectura principalmente en el nivel del entorno de desarrollo con especial hincapié en dos tecnologías: Docker y .NET.</span><span class="sxs-lookup"><span data-stu-id="35ffb-131">This guide provides foundational development and architectural guidance primarily at a development environment level with a focus on two technologies: Docker and .NET.</span></span> <span data-ttu-id="35ffb-132">Nuestra intención es que lea esta guía cuando reflexione sobre el diseño de las aplicaciones sin centrarse en la infraestructura (en la nube o local) de su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="35ffb-132">Our intention is that you read this guide when thinking about your application design without focusing on the infrastructure (cloud or on-premises) of your production environment.</span></span> <span data-ttu-id="35ffb-133">Tomará decisiones sobre la infraestructura más adelante, cuando cree aplicaciones listas para la producción.</span><span class="sxs-lookup"><span data-stu-id="35ffb-133">You will make decisions about your infrastructure later, when you create your production-ready applications.</span></span> <span data-ttu-id="35ffb-134">Por lo tanto, esta guía está diseñada para ser independiente de la infraestructura y centrarse en el desarrollo y el entorno.</span><span class="sxs-lookup"><span data-stu-id="35ffb-134">Therefore, this guide is intended to be infrastructure agnostic and more development-environment-centric.</span></span>

<span data-ttu-id="35ffb-135">Una vez que haya estudiado esta guía, el siguiente paso que debería dar es obtener información sobre los microservicios listos para la producción en Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="35ffb-135">After you have studied this guide, your next step would be to learn about production-ready microservices on Microsoft Azure.</span></span>

## <a name="version"></a><span data-ttu-id="35ffb-136">Versión</span><span class="sxs-lookup"><span data-stu-id="35ffb-136">Version</span></span>

<span data-ttu-id="35ffb-137">Esta guía se ha revisado para abarcar la versión **.NET 5** junto con muchas actualizaciones adicionales relacionadas con la misma "oleada" de tecnologías (es decir, Azure y otras tecnologías de terceros) que coincidan en el tiempo con la versión de .NET 5.</span><span class="sxs-lookup"><span data-stu-id="35ffb-137">This guide has been revised to cover **.NET 5** version along with many additional updates related to the same “wave” of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET 5 release.</span></span> <span data-ttu-id="35ffb-138">Este es el motivo por el que la versión del libro se ha actualizado también a la versión **5.0**.</span><span class="sxs-lookup"><span data-stu-id="35ffb-138">That’s why the book version has also been updated to version **5.0**.</span></span>

## <a name="what-this-guide-does-not-cover"></a><span data-ttu-id="35ffb-139">Aspectos no tratados en esta guía</span><span class="sxs-lookup"><span data-stu-id="35ffb-139">What this guide does not cover</span></span>

<span data-ttu-id="35ffb-140">Esta guía no se centra en el ciclo de vida de la aplicación, DevOps, las canalizaciones CI/CD ni el trabajo de equipo.</span><span class="sxs-lookup"><span data-stu-id="35ffb-140">This guide does not focus on the application lifecycle, DevOps, CI/CD pipelines, or team work.</span></span> <span data-ttu-id="35ffb-141">La guía complementaria [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) (Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y herramientas de Microsoft) se centra en esas cuestiones.</span><span class="sxs-lookup"><span data-stu-id="35ffb-141">The complementary guide [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) focuses on that subject.</span></span> <span data-ttu-id="35ffb-142">La guía actual tampoco proporciona detalles de implementación de la infraestructura de Azure, como información sobre orquestadores específicos.</span><span class="sxs-lookup"><span data-stu-id="35ffb-142">The current guide also does not provide implementation details on Azure infrastructure, such as information on specific orchestrators.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="35ffb-143">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="35ffb-143">Additional resources</span></span>

- <span data-ttu-id="35ffb-144">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft; libro electrónico descargable)</span><span class="sxs-lookup"><span data-stu-id="35ffb-144">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book)</span></span>  
    <https://aka.ms/dockerlifecycleebook>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="35ffb-145">Destinatarios de esta guía</span><span class="sxs-lookup"><span data-stu-id="35ffb-145">Who should use this guide</span></span>

<span data-ttu-id="35ffb-146">Esta guía se ha escrito para desarrolladores y arquitectos de soluciones que no están familiarizados con el desarrollo de aplicaciones basado en Docker y la arquitectura basada en microservicios.</span><span class="sxs-lookup"><span data-stu-id="35ffb-146">We wrote this guide for developers and solution architects who are new to Docker-based application development and to microservices-based architecture.</span></span> <span data-ttu-id="35ffb-147">Esta guía será de su interés si quiere obtener información sobre cómo crear arquitecturas, diseñar e implementar aplicaciones de prueba de concepto con tecnologías de desarrollo de Microsoft (con un hincapié especial en .NET) y con contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="35ffb-147">This guide is for you if you want to learn how to architect, design, and implement proof-of-concept applications with Microsoft development technologies (with special focus on .NET) and with Docker containers.</span></span>

<span data-ttu-id="35ffb-148">También le resultará útil si es el responsable de tomar decisiones técnicas (por ejemplo, un arquitecto empresarial) y necesita una descripción de la arquitectura y la tecnología antes de decidir qué enfoque tomar para el diseño de aplicaciones distribuidas tanto nuevas como modernas.</span><span class="sxs-lookup"><span data-stu-id="35ffb-148">You will also find this guide useful if you are a technical decision maker, such as an enterprise architect, who wants an architecture and technology overview before you decide on what approach to select for new and modern distributed applications.</span></span>

### <a name="how-to-use-this-guide"></a><span data-ttu-id="35ffb-149">Cómo usar esta guía</span><span class="sxs-lookup"><span data-stu-id="35ffb-149">How to use this guide</span></span>

<span data-ttu-id="35ffb-150">La primera parte de esta guía presenta los contenedores de Docker, describe cómo elegir entre .NET Core y .NET Framework como marco de desarrollo y proporciona una visión general de los microservicios.</span><span class="sxs-lookup"><span data-stu-id="35ffb-150">The first part of this guide introduces Docker containers, discusses how to choose between .NET Core and the .NET Framework as a development framework, and provides an overview of microservices.</span></span> <span data-ttu-id="35ffb-151">Este contenido está destinado a arquitectos y responsables de la toma de decisiones técnicas que quieren obtener información general pero que no necesitan centrarse en los detalles de la implementación de código.</span><span class="sxs-lookup"><span data-stu-id="35ffb-151">This content is for architects and technical decision makers who want an overview but don't need to focus on code implementation details.</span></span>

<span data-ttu-id="35ffb-152">La segunda parte de la guía comienza con la sección [Proceso de desarrollo de aplicaciones basadas en Docker](./docker-application-development-process/index.md).</span><span class="sxs-lookup"><span data-stu-id="35ffb-152">The second part of the guide starts with the [Development process for Docker based applications](./docker-application-development-process/index.md) section.</span></span> <span data-ttu-id="35ffb-153">Se centra en los patrones de desarrollo y microservicios empleados en la implementación de aplicaciones que usan .NET Core y Docker.</span><span class="sxs-lookup"><span data-stu-id="35ffb-153">It focuses on the development and microservice patterns for implementing applications using .NET Core and Docker.</span></span> <span data-ttu-id="35ffb-154">Esta sección será de gran interés para los desarrolladores y los arquitectos que quieran centrarse en el código, en los patrones y los detalles de implementación.</span><span class="sxs-lookup"><span data-stu-id="35ffb-154">This section will be of most interest to developers and architects who want to focus on code and on patterns and implementation details.</span></span>

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a><span data-ttu-id="35ffb-155">Aplicación de referencia relacionada de microservicios y basada en contenedor: eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="35ffb-155">Related microservice and container-based reference application: eShopOnContainers</span></span>

<span data-ttu-id="35ffb-156">La aplicación eShopOnContainers es una aplicación de referencia de código abierto para .NET y microservicios que está diseñada para implementarse mediante contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="35ffb-156">The eShopOnContainers application is an open-source reference app for .NET and microservices that is designed to be deployed using Docker containers.</span></span> <span data-ttu-id="35ffb-157">La aplicación consta de varios subsistemas, incluidos varios front-end de interfaz de usuario de almacén electrónico (una aplicación web de MVC, una SPA web y una aplicación móvil nativa).</span><span class="sxs-lookup"><span data-stu-id="35ffb-157">The application consists of multiple subsystems, including several e-store UI front-ends (a Web MVC app, a Web SPA, and a native mobile app).</span></span> <span data-ttu-id="35ffb-158">También incluye microservicios y contenedores de back-end para todas las operaciones del lado servidor necesarias.</span><span class="sxs-lookup"><span data-stu-id="35ffb-158">It also includes the back-end microservices and containers for all required server-side operations.</span></span>

<span data-ttu-id="35ffb-159">El propósito de la aplicación es presentar patrones arquitectónicos.</span><span class="sxs-lookup"><span data-stu-id="35ffb-159">The purpose of the application is to showcase architectural patterns.</span></span> <span data-ttu-id="35ffb-160">**NO SE TRATA DE UNA PLANTILLA LISTA PARA PRODUCCIÓN** para iniciar aplicaciones del mundo real.</span><span class="sxs-lookup"><span data-stu-id="35ffb-160">**IT IS NOT A PRODUCTION-READY TEMPLATE** to start real-world applications.</span></span> <span data-ttu-id="35ffb-161">De hecho, la aplicación se encuentra en un estado beta permanente, ya que también se usa para probar nuevas tecnologías potencialmente interesantes a medida que aparecen.</span><span class="sxs-lookup"><span data-stu-id="35ffb-161">In fact, the application is in a permanent beta state, as it's also used to test new potentially interesting technologies as they show up.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="35ffb-162">Envíenos sus comentarios.</span><span class="sxs-lookup"><span data-stu-id="35ffb-162">Send us your feedback!</span></span>

<span data-ttu-id="35ffb-163">Hemos creado esta guía para ayudarle a entender la arquitectura de aplicaciones y microservicios en contenedor en .NET.</span><span class="sxs-lookup"><span data-stu-id="35ffb-163">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="35ffb-164">La guía y la aplicación de referencia relacionada irán evolucionando, por lo que le agradecemos sus comentarios.</span><span class="sxs-lookup"><span data-stu-id="35ffb-164">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="35ffb-165">Si tiene comentarios sobre cómo se puede mejorar esta guía, envíelos a <https://aka.ms/ebookfeedback>.</span><span class="sxs-lookup"><span data-stu-id="35ffb-165">If you have comments about how this guide can be improved, submit feedback at <https://aka.ms/ebookfeedback>.</span></span>

## <a name="credits"></a><span data-ttu-id="35ffb-166">Créditos</span><span class="sxs-lookup"><span data-stu-id="35ffb-166">Credits</span></span>

<span data-ttu-id="35ffb-167">Coautores:</span><span class="sxs-lookup"><span data-stu-id="35ffb-167">Co-Authors:</span></span>

> <span data-ttu-id="35ffb-168">**Cesar de la Torre**, administrador de programas sénior del equipo de producto de .NET, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="35ffb-168">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>
>
> <span data-ttu-id="35ffb-169">**Bill Wagner**, desarrollador de contenido sénior de C+E, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="35ffb-169">**Bill Wagner**, Sr. Content Developer, C+E, Microsoft Corp.</span></span>
>
> <span data-ttu-id="35ffb-170">**Mike Rousos**, ingeniero de software principal del equipo de CAT de la división de desarrollo, Microsoft</span><span class="sxs-lookup"><span data-stu-id="35ffb-170">**Mike Rousos**, Principal Software Engineer, DevDiv CAT team, Microsoft</span></span>

<span data-ttu-id="35ffb-171">Editores:</span><span class="sxs-lookup"><span data-stu-id="35ffb-171">Editors:</span></span>

> <span data-ttu-id="35ffb-172">**Mike Pope**</span><span class="sxs-lookup"><span data-stu-id="35ffb-172">**Mike Pope**</span></span>
>
> <span data-ttu-id="35ffb-173">**Steve Hoag**</span><span class="sxs-lookup"><span data-stu-id="35ffb-173">**Steve Hoag**</span></span>

<span data-ttu-id="35ffb-174">Participantes y revisores:</span><span class="sxs-lookup"><span data-stu-id="35ffb-174">Participants and reviewers:</span></span>

> <span data-ttu-id="35ffb-175">**Jeffrey Richter**, ingeniero de software asociado del equipo de Azure, Microsoft</span><span class="sxs-lookup"><span data-stu-id="35ffb-175">**Jeffrey Richter**, Partner Software Eng, Azure team, Microsoft</span></span>
>
> <span data-ttu-id="35ffb-176">**Jimmy Bogard**, arquitecto jefe de Headspring</span><span class="sxs-lookup"><span data-stu-id="35ffb-176">**Jimmy Bogard**, Chief Architect at Headspring</span></span>
>
> <span data-ttu-id="35ffb-177">**Udi Dahan**, fundador y director general de Particular Software</span><span class="sxs-lookup"><span data-stu-id="35ffb-177">**Udi Dahan**, Founder & CEO, Particular Software</span></span>
>
> <span data-ttu-id="35ffb-178">**Jimmy Nilsson**, cofundador y director general de Factor10</span><span class="sxs-lookup"><span data-stu-id="35ffb-178">**Jimmy Nilsson**, Co-founder and CEO of Factor10</span></span>
>
> <span data-ttu-id="35ffb-179">**Glenn Condron**, director de programas sénior del equipo de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="35ffb-179">**Glenn Condron**, Sr. Program Manager, ASP.NET team</span></span>
>
> <span data-ttu-id="35ffb-180">**Mark Fussell**, responsable principal de administración de programas del equipo de Azure Service Fabric, Microsoft</span><span class="sxs-lookup"><span data-stu-id="35ffb-180">**Mark Fussell**, Principal PM Lead, Azure Service Fabric team, Microsoft</span></span>
>
> <span data-ttu-id="35ffb-181">**Diego Vega**, responsable de administración de programas del equipo de Entity Framework, Microsoft</span><span class="sxs-lookup"><span data-stu-id="35ffb-181">**Diego Vega**, PM Lead, Entity Framework team, Microsoft</span></span>
>
> <span data-ttu-id="35ffb-182">**Barry Dorrans**, director de programas de seguridad sénior</span><span class="sxs-lookup"><span data-stu-id="35ffb-182">**Barry Dorrans**, Sr. Security Program Manager</span></span>
>
> <span data-ttu-id="35ffb-183">**Rowan Miller**, director de programas sénior, Microsoft</span><span class="sxs-lookup"><span data-stu-id="35ffb-183">**Rowan Miller**, Sr. Program Manager, Microsoft</span></span>
>
> <span data-ttu-id="35ffb-184">**Ankit Asthana**, director principal de administración de programas del equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="35ffb-184">**Ankit Asthana**, Principal PM Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="35ffb-185">**Scott Hunter**, director asociado de administración de programas del equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="35ffb-185">**Scott Hunter**, Partner Director PM, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="35ffb-186">**Nish Anil**, director de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="35ffb-186">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="35ffb-187">**Dylan Reisenberger**, arquitecto y responsable de desarrollo de Polly</span><span class="sxs-lookup"><span data-stu-id="35ffb-187">**Dylan Reisenberger**, Architect and Dev Lead at Polly</span></span>
>
> <span data-ttu-id="35ffb-188">**Steve "ardalis" Smith**: instructor y arquitecto de software de [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="35ffb-188">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>
>
> <span data-ttu-id="35ffb-189">**Cooper Ian**, arquitecto de codificación de Brighter</span><span class="sxs-lookup"><span data-stu-id="35ffb-189">**Ian Cooper**, Coding Architect at Brighter</span></span>
>
> <span data-ttu-id="35ffb-190">**Unai Zorrilla**, arquitecto y responsable de desarrollo de Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="35ffb-190">**Unai Zorrilla**, Architect and Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="35ffb-191">**Eduard Tomas**, responsable de desarrollo de Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="35ffb-191">**Eduard Tomas**, Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="35ffb-192">**Ramon Tomas**, desarrollador de Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="35ffb-192">**Ramon Tomas**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="35ffb-193">**David Sanz**, desarrollador de Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="35ffb-193">**David Sanz**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="35ffb-194">**Javier Valero**, director de operaciones de Grupo Solutio</span><span class="sxs-lookup"><span data-stu-id="35ffb-194">**Javier Valero**, Chief Operating Officer at Grupo Solutio</span></span>
>
> <span data-ttu-id="35ffb-195">**Pierre Millet**, consultor sénior, Microsoft</span><span class="sxs-lookup"><span data-stu-id="35ffb-195">**Pierre Millet**, Sr. Consultant, Microsoft</span></span>
>
> <span data-ttu-id="35ffb-196">**Michael Friis**, administrador de productos de Docker Inc.</span><span class="sxs-lookup"><span data-stu-id="35ffb-196">**Michael Friis**, Product Manager, Docker Inc</span></span>
>
> <span data-ttu-id="35ffb-197">**Charles Lowell**, ingeniero de software del equipo de CAT de VS, Microsoft</span><span class="sxs-lookup"><span data-stu-id="35ffb-197">**Charles Lowell**, Software Engineer, VS CAT team, Microsoft</span></span>
>
> <span data-ttu-id="35ffb-198">**Miguel Veloso**, ingeniero de desarrollo de software en Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="35ffb-198">**Miguel Veloso**, Software Development Engineer at Plain Concepts</span></span>
>
> <span data-ttu-id="35ffb-199">**Sumit Ghosh**, asesor principal en Neudesic</span><span class="sxs-lookup"><span data-stu-id="35ffb-199">**Sumit Ghosh**, Principal Consultant at Neudesic</span></span>

## <a name="copyright"></a><span data-ttu-id="35ffb-200">Copyright</span><span class="sxs-lookup"><span data-stu-id="35ffb-200">Copyright</span></span>

<span data-ttu-id="35ffb-201">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="35ffb-201">PUBLISHED BY</span></span>

<span data-ttu-id="35ffb-202">Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio</span><span class="sxs-lookup"><span data-stu-id="35ffb-202">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="35ffb-203">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="35ffb-203">A division of Microsoft Corporation</span></span>

<span data-ttu-id="35ffb-204">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="35ffb-204">One Microsoft Way</span></span>

<span data-ttu-id="35ffb-205">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="35ffb-205">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="35ffb-206">Copyright © 2020 de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="35ffb-206">Copyright © 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="35ffb-207">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="35ffb-207">All rights reserved.</span></span> <span data-ttu-id="35ffb-208">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="35ffb-208">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="35ffb-209">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="35ffb-209">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="35ffb-210">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="35ffb-210">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="35ffb-211">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="35ffb-211">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="35ffb-212">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="35ffb-212">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="35ffb-213">Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="35ffb-213">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="35ffb-214">Mac y macOS son marcas comerciales de Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="35ffb-214">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="35ffb-215">El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.</span><span class="sxs-lookup"><span data-stu-id="35ffb-215">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="35ffb-216">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="35ffb-216">All other marks and logos are property of their respective owners.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="35ffb-217">Siguiente</span><span class="sxs-lookup"><span data-stu-id="35ffb-217">Next</span></span>](container-docker-introduction/index.md)
