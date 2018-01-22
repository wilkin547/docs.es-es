---
title: WCF Data Services 4.5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b5b27a51dcec17f72b86e77a7ee2ab773aec1dc3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="24a70-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="24a70-102">WCF Data Services 4.5</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="24a70-103"> (antes conocido como "ADO.NET Data Services") es un componente de .NET Framework que permite crear servicios que usan [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] para exponer y usar datos a través de la Web o de una intranet mediante la semántica de [transferencia de estado de representación (REST)](http://go.microsoft.com/fwlink/?LinkId=113919).</span><span class="sxs-lookup"><span data-stu-id="24a70-103"> (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](http://go.microsoft.com/fwlink/?LinkId=113919).</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="24a70-104"> expone los datos como recursos direccionables a través de identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="24a70-104"> exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="24a70-105">Para tener acceso a los datos y cambiarlos se utilizan los verbos HTTP estándar GET, PUT, POST y DELETE.</span><span class="sxs-lookup"><span data-stu-id="24a70-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="24a70-106"> usa las convenciones del modelo entidad-relación de [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) para exponer los recursos como conjuntos de entidades que están relacionadas por medio de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="24a70-106"> uses the entity-relationship conventions of the [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="24a70-107"> usa el protocolo de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] para direccionar y actualizar los recursos.</span><span class="sxs-lookup"><span data-stu-id="24a70-107"> uses the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol for addressing and updating resources.</span></span> <span data-ttu-id="24a70-108">De esta manera, puede tener acceso a estos servicios desde cualquier cliente que admita [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24a70-108">In this way, you can access these services from any client that supports [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="24a70-109"> le permite solicitar datos a los recursos y escribir en ellos mediante formatos de transferencia conocidos: Atom, un conjunto de estándares para intercambiar y actualizar datos como XML, y Notación de objetos JavaScript (JSON), un formato de intercambio de datos basado en texto muy usado en aplicaciones AJAX.</span><span class="sxs-lookup"><span data-stu-id="24a70-109"> enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX application.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="24a70-110"> puede exponer datos procedentes de varios orígenes como fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24a70-110"> can expose data that originates from various sources as [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span> <span data-ttu-id="24a70-111">Las herramientas de Visual Studio facilitan la creación de un servicio basado en [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] mediante el uso de un modelo de datos de ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="24a70-111">Visual Studio tools make it easier for you to create an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="24a70-112">También puede crear fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] basadas en clases de Common Language Runtime (CLR) e incluso en datos enlazados en tiempo de ejecución o datos sin tipo.</span><span class="sxs-lookup"><span data-stu-id="24a70-112">You can also create [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="24a70-113"> también incluye dos conjuntos de bibliotecas de cliente, uno para las aplicaciones cliente de .NET Framework generales y otro específicamente para las aplicaciones basadas en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="24a70-113"> also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="24a70-114">Estas bibliotecas cliente proporcionan un modelo de programación basado en objetos cuando se tiene acceso a una fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] desde entornos como .NET Framework y Silverlight.</span><span class="sxs-lookup"><span data-stu-id="24a70-114">These client libraries provide an object-based programming model when you access an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed from environments such as the .NET Framework and Silverlight.</span></span>  
  
## <a name="where-should-i-start"></a><span data-ttu-id="24a70-115">¿Por dónde empiezo?</span><span class="sxs-lookup"><span data-stu-id="24a70-115">Where Should I Start?</span></span>  
 <span data-ttu-id="24a70-116">En función de sus intereses, puede comenzar con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] en uno de los siguientes temas.</span><span class="sxs-lookup"><span data-stu-id="24a70-116">Depending on your interests, consider getting started with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] in one of the following topics.</span></span>  
  
 <span data-ttu-id="24a70-117">Deseo comenzar de inmediato…</span><span class="sxs-lookup"><span data-stu-id="24a70-117">I want to jump right in…</span></span>  
 -   [<span data-ttu-id="24a70-118">Inicio rápido</span><span class="sxs-lookup"><span data-stu-id="24a70-118">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [<span data-ttu-id="24a70-119">Introducción</span><span class="sxs-lookup"><span data-stu-id="24a70-119">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
  
-   [<span data-ttu-id="24a70-120">Inicio rápido de Silverlight</span><span class="sxs-lookup"><span data-stu-id="24a70-120">Silverlight Quickstart</span></span>](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [<span data-ttu-id="24a70-121">Inicio rápido de Silverlight para desarrollo de Windows Phone</span><span class="sxs-lookup"><span data-stu-id="24a70-121">Silverlight Quickstart for Windows Phone Development</span></span>](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
 <span data-ttu-id="24a70-122">Deseo ver algo de código…</span><span class="sxs-lookup"><span data-stu-id="24a70-122">Just show me some code…</span></span>  
 -   [<span data-ttu-id="24a70-123">Inicio rápido</span><span class="sxs-lookup"><span data-stu-id="24a70-123">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [<span data-ttu-id="24a70-124">Cómo: ejecutar consultas de servicios de datos</span><span class="sxs-lookup"><span data-stu-id="24a70-124">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
-   [<span data-ttu-id="24a70-125">Cómo: enlazar datos a elementos de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="24a70-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)  
  
 <span data-ttu-id="24a70-126">Deseo saber más sobre [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]…</span><span class="sxs-lookup"><span data-stu-id="24a70-126">I want to know more about [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]…</span></span>  
 -   [<span data-ttu-id="24a70-127">Notas del producto: introducción a OData</span><span class="sxs-lookup"><span data-stu-id="24a70-127">Whitepaper: Introducing OData</span></span>](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [<span data-ttu-id="24a70-128">Sitio web de Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="24a70-128">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
-   [<span data-ttu-id="24a70-129">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="24a70-129">OData: SDK</span></span>](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
-   [<span data-ttu-id="24a70-130">OData: preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="24a70-130">OData: Frequently Asked Questions</span></span>](http://go.microsoft.com/fwlink/?LinkId=185867)  
  
 <span data-ttu-id="24a70-131">Deseo ver algunos vídeos…</span><span class="sxs-lookup"><span data-stu-id="24a70-131">I want to watch some videos…</span></span>  
 -   [<span data-ttu-id="24a70-132">Guía para principiantes de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="24a70-132">Beginner's Guide to WCF Data Services</span></span>](http://go.microsoft.com/fwlink/?LinkId=220864)  
  
-   [<span data-ttu-id="24a70-133">Vídeos para desarrolladores de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="24a70-133">WCF Data Services Developer Videos</span></span>](http://go.microsoft.com/fwlink/?LinkId=220861)  
  
-   [<span data-ttu-id="24a70-134">OData: sitio web para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="24a70-134">OData: Developers Web site</span></span>](http://go.microsoft.com/fwlink/?LinkId=185866)  
  
 <span data-ttu-id="24a70-135">Deseo ver ejemplos completos</span><span class="sxs-lookup"><span data-stu-id="24a70-135">I want to see end-to-end samples</span></span>  
 -   [<span data-ttu-id="24a70-136">Ejemplos de documentación de Servicios de datos de WCF en la galería de ejemplos de MSDN</span><span class="sxs-lookup"><span data-stu-id="24a70-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](http://go.microsoft.com/fwlink/?LinkID=220865)  
  
-   [<span data-ttu-id="24a70-137">Otros ejemplos de Servicios de datos de WCF en la galería de ejemplos de MSDN</span><span class="sxs-lookup"><span data-stu-id="24a70-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](http://go.microsoft.com/fwlink/?LinkId=220866)  
  
-   [<span data-ttu-id="24a70-138">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="24a70-138">OData: SDK</span></span>](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
 <span data-ttu-id="24a70-139">¿Cómo se integra con Visual Studio?</span><span class="sxs-lookup"><span data-stu-id="24a70-139">How does it integrate with Visual Studio?</span></span>  
 -   [<span data-ttu-id="24a70-140">Generar la biblioteca cliente del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="24a70-140">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
  
-   [<span data-ttu-id="24a70-141">Creación del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="24a70-141">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
  
-   [<span data-ttu-id="24a70-142">Proveedor de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="24a70-142">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
  
 <span data-ttu-id="24a70-143">¿Qué me permite hacer?</span><span class="sxs-lookup"><span data-stu-id="24a70-143">What can I do with it?</span></span>  
 -   [<span data-ttu-id="24a70-144">Información general</span><span class="sxs-lookup"><span data-stu-id="24a70-144">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
  
-   [<span data-ttu-id="24a70-145">Notas del producto: introducción a OData</span><span class="sxs-lookup"><span data-stu-id="24a70-145">Whitepaper: Introducing OData</span></span>](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [<span data-ttu-id="24a70-146">Escenarios de aplicación</span><span class="sxs-lookup"><span data-stu-id="24a70-146">Application Scenarios</span></span>](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)  
  
 <span data-ttu-id="24a70-147">Deseo usar Silverlight…</span><span class="sxs-lookup"><span data-stu-id="24a70-147">I want to use Silverlight…</span></span>  
 -   [<span data-ttu-id="24a70-148">Inicio rápido de Silverlight</span><span class="sxs-lookup"><span data-stu-id="24a70-148">Silverlight Quickstart</span></span>](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [<span data-ttu-id="24a70-149">Servicios de datos de WCF (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="24a70-149">WCF Data Services (Silverlight)</span></span>](http://go.microsoft.com/fwlink/?LinkID=143149)  
  
-   [<span data-ttu-id="24a70-150">Introducción a Silverlight</span><span class="sxs-lookup"><span data-stu-id="24a70-150">Getting Started with Silverlight</span></span>](http://go.microsoft.com/fwlink/?LinkId=148366)  
  
 <span data-ttu-id="24a70-151">Deseo crear una aplicación Windows Phone…</span><span class="sxs-lookup"><span data-stu-id="24a70-151">I want to create a Windows Phone application…</span></span>  
 -   [<span data-ttu-id="24a70-152">Inicio rápido de Silverlight para desarrollo de Windows Phone</span><span class="sxs-lookup"><span data-stu-id="24a70-152">Silverlight Quickstart for Windows Phone Development</span></span>](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
-   [<span data-ttu-id="24a70-153">Cliente de Open Data Protocol (OData) para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="24a70-153">Open Data Protocol (OData) Client for Windows Phone</span></span>](http://go.microsoft.com/fwlink/?LinkID=208749)  
  
 <span data-ttu-id="24a70-154">Deseo usar LINQ…</span><span class="sxs-lookup"><span data-stu-id="24a70-154">I want to use LINQ…</span></span>  
 -   [<span data-ttu-id="24a70-155">Consultar el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="24a70-155">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
  
-   [<span data-ttu-id="24a70-156">Consideraciones sobre LINQ</span><span class="sxs-lookup"><span data-stu-id="24a70-156">LINQ Considerations</span></span>](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)  
  
-   [<span data-ttu-id="24a70-157">Cómo: ejecutar consultas de servicios de datos</span><span class="sxs-lookup"><span data-stu-id="24a70-157">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
 <span data-ttu-id="24a70-158">Necesito un poco más información…</span><span class="sxs-lookup"><span data-stu-id="24a70-158">I still need some more information…</span></span>  
 -   [<span data-ttu-id="24a70-159">Blog del equipo de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="24a70-159">WCF Data Services Team Blog</span></span>](http://go.microsoft.com/fwlink/?LinkID=150511)  
  
-   [<span data-ttu-id="24a70-160">Recursos</span><span class="sxs-lookup"><span data-stu-id="24a70-160">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)  
  
-   [<span data-ttu-id="24a70-161">Centro para desarrolladores de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="24a70-161">WCF Data Services Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=220868)  
  
-   [<span data-ttu-id="24a70-162">Sitio web de Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="24a70-162">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
## <a name="in-this-section"></a><span data-ttu-id="24a70-163">En esta sección</span><span class="sxs-lookup"><span data-stu-id="24a70-163">In This Section</span></span>  
 [<span data-ttu-id="24a70-164">Información general</span><span class="sxs-lookup"><span data-stu-id="24a70-164">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
 <span data-ttu-id="24a70-165">Proporciona información general sobre las características y la funcionalidad disponibles en [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24a70-165">Provides an overview of the features and functionality available in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="24a70-166">Novedades de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="24a70-166">What's New in WCF Data Services</span></span>](http://msdn.microsoft.com/library/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)  
 <span data-ttu-id="24a70-167">Describe nuevas funciones de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] y la compatibilidad con las nuevas características de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24a70-167">Describes new functionality in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] and support for new [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] features.</span></span>  
  
 [<span data-ttu-id="24a70-168">Introducción</span><span class="sxs-lookup"><span data-stu-id="24a70-168">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 <span data-ttu-id="24a70-169">Describe cómo exponer y consumir fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] mediante [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24a70-169">Describes how to expose and consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds by using [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="24a70-170">Definir Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="24a70-170">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 <span data-ttu-id="24a70-171">Describe cómo crear y configurar un servicio de datos que expone fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24a70-171">Describes how to create and configure a data service that exposes [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span>  
  
 [<span data-ttu-id="24a70-172">Biblioteca cliente de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="24a70-172">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 <span data-ttu-id="24a70-173">Describe cómo usar las bibliotecas cliente para consumir fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] desde una aplicación cliente de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="24a70-173">Describes how to use client libraries to consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds from a .NET Framework client application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24a70-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="24a70-174">See Also</span></span>  
 [<span data-ttu-id="24a70-175">Transferencia de estado representacional (REST)</span><span class="sxs-lookup"><span data-stu-id="24a70-175">Representational State Transfer (REST)</span></span>](http://go.microsoft.com/fwlink/?LinkId=113919)
