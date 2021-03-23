---
title: Biblioteca cliente de Data Services de WCF
description: Obtenga información acerca de cómo usar las bibliotecas de cliente de Servicios de datos de WCF para obtener acceso y cambiar los datos de una aplicación cliente de .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: 3d8a0f869454ce24d847127c2097239886f3395b
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805667"
---
# <a name="wcf-data-services-client-library"></a><span data-ttu-id="77ea7-103">Biblioteca cliente de Data Services de WCF</span><span class="sxs-lookup"><span data-stu-id="77ea7-103">WCF Data Services Client Library</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="77ea7-104">Cualquier aplicación puede interactuar con un servicio de datos basado en Open Data Protocol (OData) si puede enviar una solicitud HTTP y procesar la fuente de OData que devuelve un servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="77ea7-104">Any application can interact with an Open Data Protocol (OData)-based data service if it can send an HTTP request and process the OData feed that a data service returns.</span></span> <span data-ttu-id="77ea7-105">Esta interoperabilidad le permite tener acceso a los servicios basados en OData desde una amplia gama de aplicaciones habilitadas para Web.</span><span class="sxs-lookup"><span data-stu-id="77ea7-105">This interoperability enables you to access OData-based services from a broad range of Web-enabled applications.</span></span> <span data-ttu-id="77ea7-106">Servicios de datos de WCF incluye bibliotecas de cliente que proporcionan una experiencia de programación más enriquecida cuando se usan fuentes de OData desde .NET Framework o aplicaciones basadas en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="77ea7-106">WCF Data Services includes client libraries that provide a richer programming experience when you consume OData feeds from .NET Framework or Silverlight-based applications.</span></span>  
  
 <span data-ttu-id="77ea7-107">Las dos clases principales de la biblioteca cliente son <xref:System.Data.Services.Client.DataServiceContext> y <xref:System.Data.Services.Client.DataServiceQuery%601>.</span><span class="sxs-lookup"><span data-stu-id="77ea7-107">The two main classes of the client library are the <xref:System.Data.Services.Client.DataServiceContext> class and the <xref:System.Data.Services.Client.DataServiceQuery%601> class.</span></span> <span data-ttu-id="77ea7-108">La clase <xref:System.Data.Services.Client.DataServiceContext> encapsula las operaciones admitidas en un servicio de datos determinado.</span><span class="sxs-lookup"><span data-stu-id="77ea7-108">The <xref:System.Data.Services.Client.DataServiceContext> class encapsulates operations that are supported against a specified data service.</span></span> <span data-ttu-id="77ea7-109">Aunque los servicios de OData no tienen estado, el contexto no es.</span><span class="sxs-lookup"><span data-stu-id="77ea7-109">Although OData services are stateless, the context is not.</span></span> <span data-ttu-id="77ea7-110">Por lo tanto, puede utilizar la <xref:System.Data.Services.Client.DataServiceContext> clase para mantener el estado en el cliente entre las interacciones con el servicio de datos con el fin de admitir características como la administración de cambios.</span><span class="sxs-lookup"><span data-stu-id="77ea7-110">Therefore, you can use the <xref:System.Data.Services.Client.DataServiceContext> class to maintain state on the client between interactions with the data service in order to support features such as change management.</span></span> <span data-ttu-id="77ea7-111">Esta clase también administra las identidades y realiza el seguimiento de los cambios.</span><span class="sxs-lookup"><span data-stu-id="77ea7-111">This class also manages identities and tracks changes.</span></span> <span data-ttu-id="77ea7-112">La clase <xref:System.Data.Services.Client.DataServiceQuery%601> representa una consulta en un conjunto de entidades concreto.</span><span class="sxs-lookup"><span data-stu-id="77ea7-112">The <xref:System.Data.Services.Client.DataServiceQuery%601> class represents a query against a specific entity set.</span></span>  
  
 <span data-ttu-id="77ea7-113">En esta sección se describe cómo usar las bibliotecas de cliente para obtener acceso a los datos de una aplicación cliente de .NET Framework y para cambiarlos.</span><span class="sxs-lookup"><span data-stu-id="77ea7-113">This section describes how to use client libraries to access and change data from a .NET Framework client application.</span></span> <span data-ttu-id="77ea7-114">Para obtener más información sobre cómo usar la biblioteca de cliente de Servicios de datos de WCF con una aplicación basada en Silverlight, vea [servicios de datos de WCF (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)).</span><span class="sxs-lookup"><span data-stu-id="77ea7-114">For more information about how to use the WCF Data Services client library with a Silverlight-based application, see [WCF Data Services (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)).</span></span> <span data-ttu-id="77ea7-115">Hay disponibles otras bibliotecas de cliente que le permiten consumir una fuente de OData en otros tipos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="77ea7-115">Other client libraries are available that enable you to consume an OData feed in other kinds of applications.</span></span> <span data-ttu-id="77ea7-116">Para obtener más información sobre el SDK de OData, vea [el SDK de oData: código de ejemplo](https://www.odata.org/ecosystem/#sdk).</span><span class="sxs-lookup"><span data-stu-id="77ea7-116">For more information on OData SDK, see [OData SDK - Sample Code](https://www.odata.org/ecosystem/#sdk).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="77ea7-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="77ea7-117">In This Section</span></span>  

 [<span data-ttu-id="77ea7-118">Generar la biblioteca cliente del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="77ea7-118">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)  
 <span data-ttu-id="77ea7-119">Describe cómo generar una biblioteca de cliente y las clases de servicio de datos de cliente que se basan en fuentes de OData.</span><span class="sxs-lookup"><span data-stu-id="77ea7-119">Describes how to generate a client library and client data service classes that are based on OData feeds.</span></span>  
  
 [<span data-ttu-id="77ea7-120">Consultar el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="77ea7-120">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="77ea7-121">Describe cómo consultar un servicio de datos desde una aplicación basada en .NET Framework usando bibliotecas de cliente.</span><span class="sxs-lookup"><span data-stu-id="77ea7-121">Describes how to query a data service from a .NET Framework-based application by using client libraries.</span></span>  
  
 [<span data-ttu-id="77ea7-122">Carga de contenido diferido</span><span class="sxs-lookup"><span data-stu-id="77ea7-122">Loading Deferred Content</span></span>](loading-deferred-content-wcf-data-services.md)  
 <span data-ttu-id="77ea7-123">Describe cómo cargar contenido adicional no incluido en la respuesta de la consulta inicial.</span><span class="sxs-lookup"><span data-stu-id="77ea7-123">Describes how to load additional content not included in the initial query response.</span></span>  
  
 [<span data-ttu-id="77ea7-124">Actualización del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="77ea7-124">Updating the Data Service</span></span>](updating-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="77ea7-125">Describe cómo crear, modificar y eliminar entidades y relaciones usando bibliotecas de cliente.</span><span class="sxs-lookup"><span data-stu-id="77ea7-125">Describes how to create, modify, and delete entities and relationships by using the client libraries.</span></span>  
  
 [<span data-ttu-id="77ea7-126">Operaciones asincrónicas</span><span class="sxs-lookup"><span data-stu-id="77ea7-126">Asynchronous Operations</span></span>](asynchronous-operations-wcf-data-services.md)  
 <span data-ttu-id="77ea7-127">Describe los medios proporcionados por las bibliotecas de cliente para trabajar con un servicio de datos de manera asincrónica.</span><span class="sxs-lookup"><span data-stu-id="77ea7-127">Describes the facilities provided by the client libraries for working with a data service in an asynchronous manner.</span></span>  
  
 [<span data-ttu-id="77ea7-128">Procesamiento por lotes de operaciones</span><span class="sxs-lookup"><span data-stu-id="77ea7-128">Batching Operations</span></span>](batching-operations-wcf-data-services.md)  
 <span data-ttu-id="77ea7-129">Describe cómo enviar varias solicitudes al servicio de datos en un solo lote usando las bibliotecas de cliente.</span><span class="sxs-lookup"><span data-stu-id="77ea7-129">Describes how to send multiple requests to the data service in a single batch by using the client libraries.</span></span>  
  
 [<span data-ttu-id="77ea7-130">Enlazar datos a controles</span><span class="sxs-lookup"><span data-stu-id="77ea7-130">Binding Data to Controls</span></span>](binding-data-to-controls-wcf-data-services.md)  
 <span data-ttu-id="77ea7-131">Describe cómo enlazar controles a una fuente de OData devuelta por un servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="77ea7-131">Describes how to bind controls to a OData feed returned by a data service.</span></span>  
  
 [<span data-ttu-id="77ea7-132">Llamar a operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="77ea7-132">Calling Service Operations</span></span>](calling-service-operations-wcf-data-services.md)  
 <span data-ttu-id="77ea7-133">Describe cómo usar la biblioteca de cliente para llamar a operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="77ea7-133">Describes how to use the client library to call service operations.</span></span>  
  
 [<span data-ttu-id="77ea7-134">Administración del contexto del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="77ea7-134">Managing the Data Service Context</span></span>](managing-the-data-service-context-wcf-data-services.md)  
 <span data-ttu-id="77ea7-135">Describe las opciones para administrar el comportamiento de la biblioteca cliente.</span><span class="sxs-lookup"><span data-stu-id="77ea7-135">Describes options for managing the behavior of the client library.</span></span>  
  
 [<span data-ttu-id="77ea7-136">Trabajar con datos binarios</span><span class="sxs-lookup"><span data-stu-id="77ea7-136">Working with Binary Data</span></span>](working-with-binary-data-wcf-data-services.md)  
 <span data-ttu-id="77ea7-137">Describe cómo obtener acceso y cambiar los datos binarios devueltos por el servicio de datos como un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="77ea7-137">Describes how to access and change binary data returned by the data service as a data stream.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77ea7-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77ea7-138">See also</span></span>

- [<span data-ttu-id="77ea7-139">Definir Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="77ea7-139">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="77ea7-140">Introducción</span><span class="sxs-lookup"><span data-stu-id="77ea7-140">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
