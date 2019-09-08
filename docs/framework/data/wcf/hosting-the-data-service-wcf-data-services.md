---
title: Hospedar el servicio de datos (Data Services de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, Windows Communication Foundation
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
ms.openlocfilehash: ea60ac132fdd94d4e3a3676891964070b7150857
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780274"
---
# <a name="hosting-the-data-service-wcf-data-services"></a><span data-ttu-id="934f4-102">Hospedar el servicio de datos (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="934f4-102">Hosting the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="934f4-103">Con WCF Data Services, puede crear un servicio que exponga los datos como una [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] fuente.</span><span class="sxs-lookup"><span data-stu-id="934f4-103">By using WCF Data Services, you can create a service that exposes data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> <span data-ttu-id="934f4-104">Este servicio de datos se define como una clase que hereda de <xref:System.Data.Services.DataService%601>.</span><span class="sxs-lookup"><span data-stu-id="934f4-104">This data service is defined as a class that inherits from <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="934f4-105">Esta clase proporciona la funcionalidad necesaria para procesar mensajes de solicitud, realizar actualizaciones en el origen de datos y generar mensajes de respuesta, tal como requiere OData.</span><span class="sxs-lookup"><span data-stu-id="934f4-105">This class provides the functionality required to process request messages, perform updates against the data source, and generate responses messages, as required by OData.</span></span> <span data-ttu-id="934f4-106">Sin embargo, un servicio de datos no puede enlazar y escuchar en un socket de red las solicitudes HTTP entrantes.</span><span class="sxs-lookup"><span data-stu-id="934f4-106">However, a data service cannot bind to and listen on a network socket for incoming HTTP requests.</span></span> <span data-ttu-id="934f4-107">Para esta funcionalidad necesaria, el servicio de datos se basa en un componente de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="934f4-107">For this required functionality, the data service relies on a hosting component.</span></span>

 <span data-ttu-id="934f4-108">El host del servicio de datos realiza las siguientes tareas en nombre del servicio de datos:</span><span class="sxs-lookup"><span data-stu-id="934f4-108">The data service host performs the following tasks on behalf of the data service:</span></span>

- <span data-ttu-id="934f4-109">Realiza escuchas de las solicitudes y las enruta al servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="934f4-109">Listens for requests and routes these requests to the data service.</span></span>

- <span data-ttu-id="934f4-110">Crea una instancia del servicio de datos para cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="934f4-110">Creates an instance of the data service for each request.</span></span>

- <span data-ttu-id="934f4-111">Solicita al servicio de datos que procese la solicitud entrante.</span><span class="sxs-lookup"><span data-stu-id="934f4-111">Requests that the data service process the incoming request.</span></span>

- <span data-ttu-id="934f4-112">Envía la respuesta en nombre del servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="934f4-112">Sends the response on behalf of the data service.</span></span>

 <span data-ttu-id="934f4-113">Para simplificar el hospedaje de un servicio de datos, WCF Data Services está diseñado para integrarse con Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="934f4-113">To simplify hosting a data service, WCF Data Services is designed to integrate with Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="934f4-114">El servicio de datos proporciona una implementación de WCF predeterminada que actúa como host del servicio de datos en una aplicación ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="934f4-114">The data service provides a default WCF implementation that serves as the data service host in an ASP.NET application.</span></span> <span data-ttu-id="934f4-115">Por consiguiente, un servicio de datos se puede hospedar de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="934f4-115">Therefore, you can host a data service in one of the following ways:</span></span>

- <span data-ttu-id="934f4-116">En una aplicación ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="934f4-116">In an ASP.NET application.</span></span>

- <span data-ttu-id="934f4-117">En una aplicación administrada que admita servicios WCF autohospedados.</span><span class="sxs-lookup"><span data-stu-id="934f4-117">In a managed application that supports self-hosted WCF services.</span></span>

- <span data-ttu-id="934f4-118">En algún otro host del servicio de datos personalizado.</span><span class="sxs-lookup"><span data-stu-id="934f4-118">In some other custom data service host.</span></span>

## <a name="hosting-a-data-service-in-an-aspnet-application"></a><span data-ttu-id="934f4-119">Hospedar un servicio de datos en una aplicación ASP.NET</span><span class="sxs-lookup"><span data-stu-id="934f4-119">Hosting a Data Service in an ASP.NET Application</span></span>

<span data-ttu-id="934f4-120">Cuando se usa el cuadro de diálogo **Agregar nuevo elemento** de Visual Studio 2015 para definir un servicio de datos en una aplicación ASP.net, la herramienta genera dos nuevos archivos en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="934f4-120">When you use the **Add New Item** dialog in Visual Studio 2015 to define a data service in an ASP.NET application, the tool generates two new files in the project.</span></span> <span data-ttu-id="934f4-121">El primer archivo tiene una extensión `.svc` e indica al tiempo de ejecución de WCF cómo crear instancias del servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="934f4-121">The first file has a `.svc` extension and instructs the WCF runtime how to instantiate the data service.</span></span> <span data-ttu-id="934f4-122">A continuación se muestra un ejemplo de este archivo para el servicio de datos de ejemplo Northwind que se crea al completar la guía de [Inicio rápido](quickstart-wcf-data-services.md):</span><span class="sxs-lookup"><span data-stu-id="934f4-122">The following is an example of this file for the Northwind sample data service created when you complete the [quickstart](quickstart-wcf-data-services.md):</span></span>

```
<%@ ServiceHost Language="C#"
    Factory="System.Data.Services.DataServiceHostFactory,
            System.Data.Services, Version=4.0.0.0,
            Culture=neutral, PublicKeyToken=b77a5c561934e089"
    Service="NorthwindService.Northwind" %>
```

 <span data-ttu-id="934f4-123">Esta directiva indica a la aplicación que debe crear el host del servicio para la clase del servicio de datos con nombre utilizando la clase <xref:System.Data.Services.DataServiceHostFactory>.</span><span class="sxs-lookup"><span data-stu-id="934f4-123">This directive tells the application to create the service host for the named data service class by using the <xref:System.Data.Services.DataServiceHostFactory> class.</span></span>

 <span data-ttu-id="934f4-124">La página de codigos subyacente del archivo `.svc` contiene la clase que es la implementación del propio servicio de datos, el cual se define para el servicio de datos de ejemplo Northwind del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="934f4-124">The code-behind page for the `.svc` file contains the class that is the implementation of the data service itself, which is defined as follows for the Northwind sample data service:</span></span>

 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

 <span data-ttu-id="934f4-125">Dado que un servicio de datos se comporta como un servicio WCF, el servicio de datos se integra con ASP.NET y sigue el modelo de programación web de WCF.</span><span class="sxs-lookup"><span data-stu-id="934f4-125">Because a data service behaves like a WCF service, the data service integrates with ASP.NET and follows the WCF Web programming model.</span></span> <span data-ttu-id="934f4-126">Para obtener más información, vea [servicios WCF y ASP.net](../../wcf/feature-details/wcf-services-and-aspnet.md) y [modelo de programación web http de WCF](../../wcf/feature-details/wcf-web-http-programming-model.md).</span><span class="sxs-lookup"><span data-stu-id="934f4-126">For more information, see [WCF Services and ASP.NET](../../wcf/feature-details/wcf-services-and-aspnet.md) and [WCF Web HTTP Programming Model](../../wcf/feature-details/wcf-web-http-programming-model.md).</span></span>

## <a name="self-hosted-wcf-services"></a><span data-ttu-id="934f4-127">Servicios WCF autohospedados</span><span class="sxs-lookup"><span data-stu-id="934f4-127">Self-Hosted WCF Services</span></span>
 <span data-ttu-id="934f4-128">Dado que incorpora una implementación de WCF, WCF Data Services admite el hospedaje automático de un servicio de datos como un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="934f4-128">Because it incorporates a WCF implementation, WCF Data Services support self-hosting a data service as a WCF service.</span></span> <span data-ttu-id="934f4-129">Un servicio se puede autohospedar en cualquier .NET Framework aplicación, como una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="934f4-129">A service can be self-hosted in any .NET Framework application, such as a console application.</span></span> <span data-ttu-id="934f4-130">La clase <xref:System.Data.Services.DataServiceHost>, que hereda de <xref:System.ServiceModel.Web.WebServiceHost>, se utiliza para crear instancias del servicio de datos en una dirección concreta.</span><span class="sxs-lookup"><span data-stu-id="934f4-130">The <xref:System.Data.Services.DataServiceHost> class, which inherits from <xref:System.ServiceModel.Web.WebServiceHost>, is used to instantiate the data service at a specific address.</span></span>

 <span data-ttu-id="934f4-131">El autohospedaje se puede utilizar para el desarrollo y las pruebas porque facilita el despliegue y la solución de problemas del servicio.</span><span class="sxs-lookup"><span data-stu-id="934f4-131">Self-hosting can be used for development and testing because it can make it easier to deploy and troubleshoot the service.</span></span> <span data-ttu-id="934f4-132">Sin embargo, este tipo de hospedaje no ofrece las características de administración y hospedaje avanzadas proporcionadas por ASP.NET o por Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="934f4-132">However, this kind of hosting does not provide the advanced hosting and management features provided by ASP.NET or by Internet Information Services (IIS).</span></span> <span data-ttu-id="934f4-133">Para obtener más información, consulte [hospedaje en una aplicación administrada](../../wcf/feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="934f4-133">For more information, see [Hosting in a Managed Application](../../wcf/feature-details/hosting-in-a-managed-application.md).</span></span>

## <a name="defining-a-custom-data-service-host"></a><span data-ttu-id="934f4-134">Definir un host de servicio de datos personalizado</span><span class="sxs-lookup"><span data-stu-id="934f4-134">Defining a Custom Data Service Host</span></span>
 <span data-ttu-id="934f4-135">Para los casos en los que la implementación de un host de WCF sea demasiado restrictiva, se puede definir también un host personalizado para un servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="934f4-135">For cases where the WCF host implementation is too restrictive, you can also define a custom host for a data service.</span></span> <span data-ttu-id="934f4-136">Cualquier clase que implemente la interfaz <xref:System.Data.Services.IDataServiceHost> se puede utilizar como el host de red de un servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="934f4-136">Any class that implements <xref:System.Data.Services.IDataServiceHost> interface can be used as the network host for a data service.</span></span> <span data-ttu-id="934f4-137">Un host personalizado debe implementar la interfaz <xref:System.Data.Services.IDataServiceHost> y ser capaz de controlar las siguientes responsabilidades básicas del host del servicio de datos:</span><span class="sxs-lookup"><span data-stu-id="934f4-137">A custom host must implement the <xref:System.Data.Services.IDataServiceHost> interface and be able to handle the following basic responsibilities of the data service host:</span></span>

- <span data-ttu-id="934f4-138">Proporcionar la ruta de acceso raíz del servicio al servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="934f4-138">Provide the data service with the service root path.</span></span>

- <span data-ttu-id="934f4-139">Procesar la información de encabezados de respuesta y solicitud en la implementación de miembro de <xref:System.Data.Services.IDataServiceHost> adecuada.</span><span class="sxs-lookup"><span data-stu-id="934f4-139">Process request and response headers information to the appropriate <xref:System.Data.Services.IDataServiceHost> member implementation.</span></span>

- <span data-ttu-id="934f4-140">Controlar las excepciones iniciadas por el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="934f4-140">Handle exceptions raised by the data service.</span></span>

- <span data-ttu-id="934f4-141">Validar parámetros en la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="934f4-141">Validate parameters in the query string.</span></span>

## <a name="see-also"></a><span data-ttu-id="934f4-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="934f4-142">See also</span></span>

- [<span data-ttu-id="934f4-143">Definir Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="934f4-143">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="934f4-144">Exposición de los datos como servicio</span><span class="sxs-lookup"><span data-stu-id="934f4-144">Exposing Your Data as a Service</span></span>](exposing-your-data-as-a-service-wcf-data-services.md)
- [<span data-ttu-id="934f4-145">Configuración del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="934f4-145">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)
