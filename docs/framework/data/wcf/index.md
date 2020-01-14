---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: aace683b1a105445b5a3ba3de0a6a671859588b5
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937439"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="4835d-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="4835d-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="4835d-103">WCF Data Services (anteriormente conocido como "ADO.NET Data Services") es un componente de la .NET Framework que le permite crear servicios que usan Open Data Protocol (OData) para exponer y consumir datos en Internet o en una intranet mediante la semántica de [transferencia de estado representacional (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).</span><span class="sxs-lookup"><span data-stu-id="4835d-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the Open Data Protocol (OData) to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).</span></span> <span data-ttu-id="4835d-104">OData expone los datos como recursos direccionables a través de identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="4835d-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="4835d-105">Se tiene acceso a los datos y se cambian mediante los verbos HTTP de GET, PUT, POST y DELETE.</span><span class="sxs-lookup"><span data-stu-id="4835d-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="4835d-106">OData usa las convenciones de entidad-relación del [Entity Data Model](../adonet/entity-data-model.md) para exponer los recursos como conjuntos de entidades que se relacionan mediante asociaciones.</span><span class="sxs-lookup"><span data-stu-id="4835d-106">OData uses the entity-relationship conventions of the [Entity Data Model](../adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="4835d-107">WCF Data Services usa el protocolo OData para direccionar y actualizar los recursos.</span><span class="sxs-lookup"><span data-stu-id="4835d-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="4835d-108">De esta manera, puede tener acceso a estos servicios desde cualquier cliente que admita OData.</span><span class="sxs-lookup"><span data-stu-id="4835d-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="4835d-109">OData le permite solicitar y escribir datos en los recursos mediante formatos de transferencia conocidos: Atom, un conjunto de estándares para intercambiar y actualizar datos como XML, y notación de objetos JavaScript (JSON), un formato de intercambio de datos basado en texto que se usa mucho en AJAX programas.</span><span class="sxs-lookup"><span data-stu-id="4835d-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="4835d-110">WCF Data Services pueden exponer datos procedentes de varios orígenes como fuentes de OData.</span><span class="sxs-lookup"><span data-stu-id="4835d-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="4835d-111">Las herramientas de Visual Studio facilitan la creación de un servicio basado en OData mediante un modelo de datos de ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="4835d-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="4835d-112">También puede crear fuentes de OData basadas en clases de Common Language Runtime (CLR) e incluso datos enlazados en tiempo de ejecución o sin tipo.</span><span class="sxs-lookup"><span data-stu-id="4835d-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="4835d-113">WCF Data Services también incluye un conjunto de bibliotecas de cliente, uno para las aplicaciones cliente de .NET Framework general y otro específicamente para las aplicaciones basadas en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="4835d-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="4835d-114">Estas bibliotecas de cliente proporcionan un modelo de programación basado en objetos cuando se tiene acceso a una fuente de OData desde entornos como el .NET Framework y Silverlight.</span><span class="sxs-lookup"><span data-stu-id="4835d-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="4835d-115">¿Por dónde empiezo?</span><span class="sxs-lookup"><span data-stu-id="4835d-115">Where Should I Start?</span></span>

<span data-ttu-id="4835d-116">En función de sus intereses, considere la posibilidad de empezar a trabajar con WCF Data Services en uno de los siguientes temas.</span><span class="sxs-lookup"><span data-stu-id="4835d-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="4835d-117">Quiero comenzar de inmediato…</span><span class="sxs-lookup"><span data-stu-id="4835d-117">I want to jump right in...</span></span>

- [<span data-ttu-id="4835d-118">Inicio rápido</span><span class="sxs-lookup"><span data-stu-id="4835d-118">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="4835d-119">Introducción</span><span class="sxs-lookup"><span data-stu-id="4835d-119">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="4835d-120">Simplemente mostrarme parte del código...</span><span class="sxs-lookup"><span data-stu-id="4835d-120">Just show me some code...</span></span>

- [<span data-ttu-id="4835d-121">Inicio rápido</span><span class="sxs-lookup"><span data-stu-id="4835d-121">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="4835d-122">Cómo: ejecutar consultas de servicios de datos</span><span class="sxs-lookup"><span data-stu-id="4835d-122">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="4835d-123">Cómo: enlazar datos a elementos de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="4835d-123">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="4835d-124">Deseo obtener más información acerca de OData...</span><span class="sxs-lookup"><span data-stu-id="4835d-124">I want to know more about OData...</span></span>

- [<span data-ttu-id="4835d-125">Notas del producto: Introducción a OData</span><span class="sxs-lookup"><span data-stu-id="4835d-125">White paper: Introducing OData</span></span>](https://download.microsoft.com/download/E/5/A/E5A59052-EE48-4D64-897B-5F7C608165B8/IntroducingOData.pdf)
- [<span data-ttu-id="4835d-126">Sitio web Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="4835d-126">Open Data Protocol website</span></span>](https://www.odata.org/)
- [<span data-ttu-id="4835d-127">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="4835d-127">OData: SDK</span></span>](https://www.odata.org/ecosystem/)

<span data-ttu-id="4835d-128">Deseo ver ejemplos de un extremo a otro...</span><span class="sxs-lookup"><span data-stu-id="4835d-128">I want to see end-to-end samples...</span></span>

- <span data-ttu-id="4835d-129">[Inicio rápido de WCF Data Services](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span><span class="sxs-lookup"><span data-stu-id="4835d-129">[WCF Data Services Quickstart](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span></span>
- [<span data-ttu-id="4835d-130">SDK de OData: código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4835d-130">OData SDK - Sample Code</span></span>](https://www.odata.org/ecosystem/#sdk)

<span data-ttu-id="4835d-131">¿Cómo se integra con Visual Studio?</span><span class="sxs-lookup"><span data-stu-id="4835d-131">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="4835d-132">Generar la biblioteca cliente del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="4835d-132">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="4835d-133">Creación del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="4835d-133">Creating the Data Service</span></span>](creating-the-data-service.md)

- [<span data-ttu-id="4835d-134">Proveedor de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="4835d-134">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="4835d-135">¿Qué me permite hacer?</span><span class="sxs-lookup"><span data-stu-id="4835d-135">What can I do with it?</span></span>

- [<span data-ttu-id="4835d-136">Información general</span><span class="sxs-lookup"><span data-stu-id="4835d-136">Overview</span></span>](wcf-data-services-overview.md)

- [<span data-ttu-id="4835d-137">Escenarios de aplicación</span><span class="sxs-lookup"><span data-stu-id="4835d-137">Application Scenarios</span></span>](application-scenarios-wcf-data-services.md)

<span data-ttu-id="4835d-138">Deseo usar LINQ...</span><span class="sxs-lookup"><span data-stu-id="4835d-138">I want to use LINQ...</span></span>

- [<span data-ttu-id="4835d-139">Consultar el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="4835d-139">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="4835d-140">Consideraciones sobre LINQ</span><span class="sxs-lookup"><span data-stu-id="4835d-140">LINQ Considerations</span></span>](linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="4835d-141">Cómo: ejecutar consultas de servicios de datos</span><span class="sxs-lookup"><span data-stu-id="4835d-141">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="4835d-142">Todavía necesito más información...</span><span class="sxs-lookup"><span data-stu-id="4835d-142">I still need some more information...</span></span>

- [<span data-ttu-id="4835d-143">Blog del equipo de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="4835d-143">WCF Data Services Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/astoriateam/)

- [<span data-ttu-id="4835d-144">Recursos</span><span class="sxs-lookup"><span data-stu-id="4835d-144">Resources</span></span>](wcf-data-services-resources.md)

## <a name="in-this-section"></a><span data-ttu-id="4835d-145">Esta sección</span><span class="sxs-lookup"><span data-stu-id="4835d-145">In This Section</span></span>

[<span data-ttu-id="4835d-146">Información general</span><span class="sxs-lookup"><span data-stu-id="4835d-146">Overview</span></span>](wcf-data-services-overview.md)

<span data-ttu-id="4835d-147">Proporciona información general sobre las características y la funcionalidad disponibles en WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="4835d-147">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="4835d-148">[Novedades de WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="4835d-148">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="4835d-149">Describe la nueva funcionalidad de WCF Data Services y la compatibilidad con las nuevas características de OData.</span><span class="sxs-lookup"><span data-stu-id="4835d-149">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="4835d-150">Introducción</span><span class="sxs-lookup"><span data-stu-id="4835d-150">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="4835d-151">Describe cómo exponer y consumir fuentes de OData mediante WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="4835d-151">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="4835d-152">Definir Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="4835d-152">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)

<span data-ttu-id="4835d-153">Describe cómo crear y configurar un servicio de datos que exponga fuentes de OData.</span><span class="sxs-lookup"><span data-stu-id="4835d-153">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="4835d-154">Biblioteca cliente de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="4835d-154">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)

<span data-ttu-id="4835d-155">Describe cómo usar las bibliotecas de cliente para consumir fuentes de OData desde una aplicación cliente de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4835d-155">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="4835d-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="4835d-156">See also</span></span>

- [<span data-ttu-id="4835d-157">Transferencia de estado representacional (REST)</span><span class="sxs-lookup"><span data-stu-id="4835d-157">Representational State Transfer (REST)</span></span>](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
