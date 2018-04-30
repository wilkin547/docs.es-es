---
title: Publicación de metadatos para un servicio mediante código
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 51407e6d-4d87-42d5-be7c-9887b8652006
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c3d2fd1222539ec8017846069e7eda9a2c503f22
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-publish-metadata-for-a-service-using-code"></a><span data-ttu-id="875fd-102">Publicación de metadatos para un servicio mediante código</span><span class="sxs-lookup"><span data-stu-id="875fd-102">How to: Publish Metadata for a Service Using Code</span></span>
<span data-ttu-id="875fd-103">Este es uno de los dos temas de instrucciones para la publicación de metadatos para un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="875fd-103">This is one of two how-to topics that discuss publishing metadata for a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service.</span></span> <span data-ttu-id="875fd-104">Hay dos maneras de especificar cómo debería publicar metadatos un servicio: mediante un archivo de configuración y mediante código.</span><span class="sxs-lookup"><span data-stu-id="875fd-104">There are two ways to specify how a service should publish metadata, using a configuration file and using code.</span></span> <span data-ttu-id="875fd-105">En este tema se muestra cómo publicar metadatos para un servicio mediante código.</span><span class="sxs-lookup"><span data-stu-id="875fd-105">This topic shows how to publish metadata for a service using a code.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="875fd-106">En este tema se muestra cómo publicar metadatos de forma no segura.</span><span class="sxs-lookup"><span data-stu-id="875fd-106">This topic shows how to publish metadata in an unsecure manner.</span></span> <span data-ttu-id="875fd-107">Cualquier cliente puede recuperar los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="875fd-107">Any client can retrieve the metadata from the service.</span></span> <span data-ttu-id="875fd-108">Si el servicio necesita publicar los metadatos de forma segura.</span><span class="sxs-lookup"><span data-stu-id="875fd-108">If you require your service to publish metadata in a secure manner.</span></span> <span data-ttu-id="875fd-109">vea [extremo de metadatos seguros personalizado](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="875fd-109">see [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
 <span data-ttu-id="875fd-110">Para obtener más información acerca de la publicación de metadatos en un archivo de configuración, consulte [Cómo: Publicar metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="875fd-110">For more information about publishing metadata in a configuration file, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span> <span data-ttu-id="875fd-111">La publicación de metadatos permite a los clientes recuperar los metadatos mediante una solicitud GET WS-Transfer o mediante una solicitud HTTP/GET usando la cadena de solicitud `?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="875fd-111">Publishing metadata allows clients to retrieve the metadata using a WS-Transfer GET request or an HTTP/GET request using the `?wsdl` query string.</span></span> <span data-ttu-id="875fd-112">Para asegurarse de que el código funciona, debe crear un servicio básico de WCF.</span><span class="sxs-lookup"><span data-stu-id="875fd-112">To be sure that the code is working you must create a basic WCF service.</span></span> <span data-ttu-id="875fd-113">En el código siguiente, se proporciona un servicio autohospedado básico.</span><span class="sxs-lookup"><span data-stu-id="875fd-113">A basic self-hosted service is provided in the following code.</span></span>  
  
 [!code-csharp[htPublishMetadataCode#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#0)]
 [!code-vb[htPublishMetadataCode#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#0)]  
  
### <a name="to-publish-metadata-in-code"></a><span data-ttu-id="875fd-114">Publicación de metadatos mediante código</span><span class="sxs-lookup"><span data-stu-id="875fd-114">To publish metadata in code</span></span>  
  
1.  <span data-ttu-id="875fd-115">Dentro del método principal de una aplicación de consola, cree instancias de un objeto <xref:System.ServiceModel.ServiceHost> pasando el tipo de servicio y la dirección base.</span><span class="sxs-lookup"><span data-stu-id="875fd-115">Within the main method of a console application, instantiate a <xref:System.ServiceModel.ServiceHost> object by passing in the service type and the base address.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#1)]
     [!code-vb[htPublishMetadataCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#1)]  
  
2.  <span data-ttu-id="875fd-116">Cree un bloque try justo debajo del código del paso 1, esto detecta cualquier excepción que se produzca mientras se está ejecutando el servicio.</span><span class="sxs-lookup"><span data-stu-id="875fd-116">Create a try block immediately below the code for step 1, this catches any exceptions that get thrown while the service is running.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#2)]
     [!code-vb[htPublishMetadataCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#2)]  
  
     [!code-csharp[htPublishMetadataCode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#3)]
     [!code-vb[htPublishMetadataCode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#3)]  
  
3.  <span data-ttu-id="875fd-117">Compruebe si el host del servicio ya contiene un <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, si no, cree una nueva instancia de <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="875fd-117">Check to see whether the service host already contains a <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, if not, create a new <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#4)]
     [!code-vb[htPublishMetadataCode#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#4)]  
  
4.  <span data-ttu-id="875fd-118">Establezca la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en `true.`.</span><span class="sxs-lookup"><span data-stu-id="875fd-118">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true.`</span></span>  
  
     [!code-csharp[htPublishMetadataCode#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#5)]
     [!code-vb[htPublishMetadataCode#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#5)]  
  
5.  <span data-ttu-id="875fd-119">El <xref:System.ServiceModel.Description.ServiceMetadataBehavior> contiene una propiedad <xref:System.ServiceModel.Description.MetadataExporter>.</span><span class="sxs-lookup"><span data-stu-id="875fd-119">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior> contains a <xref:System.ServiceModel.Description.MetadataExporter> property.</span></span> <span data-ttu-id="875fd-120">El <xref:System.ServiceModel.Description.MetadataExporter> contiene una propiedad <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="875fd-120">The <xref:System.ServiceModel.Description.MetadataExporter> contains a <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property.</span></span> <span data-ttu-id="875fd-121">Establezca el valor de la propiedad <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> en <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>.</span><span class="sxs-lookup"><span data-stu-id="875fd-121">Set the value of the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>.</span></span> <span data-ttu-id="875fd-122">La propiedad <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> también se puede establecer en <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>.</span><span class="sxs-lookup"><span data-stu-id="875fd-122">The <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property can also be set to <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>.</span></span> <span data-ttu-id="875fd-123">Cuando se establece en <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> el exportador de metadatos genera información de la directiva con los metadatos que "se ajusta a WS-Policy 1.5.</span><span class="sxs-lookup"><span data-stu-id="875fd-123">When set to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> the metadata exporter generates policy information with the metadata that" conforms to WS-Policy 1.5.</span></span> <span data-ttu-id="875fd-124">Cuando se establece en <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>, el exportador de metadatos genera información de directivas conforme a la especificación WS-Policy 1.2.</span><span class="sxs-lookup"><span data-stu-id="875fd-124">When set to <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A> the metadata exporter generates policy information that conforms to WS-Policy 1.2.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#6)]
     [!code-vb[htPublishMetadataCode#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#6)]  
  
6.  <span data-ttu-id="875fd-125">Agregue la instancia de <xref:System.ServiceModel.Description.ServiceMetadataBehavior> a la colección de comportamientos del host del servicio.</span><span class="sxs-lookup"><span data-stu-id="875fd-125">Add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance to the service host's behaviors collection.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#7)]
     [!code-vb[htPublishMetadataCode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#7)]  
  
7.  <span data-ttu-id="875fd-126">Agregue el punto de conexión de intercambio de metadatos al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="875fd-126">Add the metadata exchange endpoint to the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#8)]
     [!code-vb[htPublishMetadataCode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#8)]  
  
8.  <span data-ttu-id="875fd-127">Agregue un punto de conexión de la aplicación al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="875fd-127">Add an application endpoint to the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#9)]
     [!code-vb[htPublishMetadataCode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#9)]  
  
    > [!NOTE]
    >  <span data-ttu-id="875fd-128">Si no agrega ningún punto de conexión al servicio, el tiempo de ejecución agregará los puntos de conexión predeterminados.</span><span class="sxs-lookup"><span data-stu-id="875fd-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="875fd-129">En este ejemplo, dado que el servicio tiene un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> establecido en `true`, el servicio tiene habilitada la publicación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="875fd-129">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, the service has publishing metadata enabled.</span></span> <span data-ttu-id="875fd-130">Para obtener más información sobre puntos de conexión predeterminados, consulte [configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="875fd-130">For more information about default endpoints, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
9. <span data-ttu-id="875fd-131">Abra el host de servicio y espere las llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="875fd-131">Open the service host and wait for incoming calls.</span></span> <span data-ttu-id="875fd-132">Cuando el usuario presione Entrar, cierre el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="875fd-132">When the user presses ENTER, close the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#10)]
     [!code-vb[htPublishMetadataCode#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#10)]  
  
10. <span data-ttu-id="875fd-133">Compile y ejecute la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="875fd-133">Build and run the console application.</span></span>  
  
11. <span data-ttu-id="875fd-134">Utilice Internet Explorer para ir a la dirección base del servicio (http://localhost:8001/MetadataSample en este ejemplo) y compruebe que la publicación de metadatos está activada.</span><span class="sxs-lookup"><span data-stu-id="875fd-134">Use Internet Explorer to browse to the base address of the service (http://localhost:8001/MetadataSample in this sample) and verify that the metadata publishing is turned on.</span></span> <span data-ttu-id="875fd-135">Debería ver una página web que dice "Servicio Simple" en la parte superior y, justo debajo, "Ha creado un servicio".</span><span class="sxs-lookup"><span data-stu-id="875fd-135">You should see a Web page displayed that says "Simple Service" at the top and immediately below "You have created a service."</span></span> <span data-ttu-id="875fd-136">Si no, un mensaje en la parte superior de la página resultante muestra: "La publicación de metadatos para este servicio está deshabilitad actualmente".</span><span class="sxs-lookup"><span data-stu-id="875fd-136">If not, a message at the top of the resulting page displays: "Metadata publishing for this service is currently disabled."</span></span>  
  
## <a name="example"></a><span data-ttu-id="875fd-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="875fd-137">Example</span></span>  
 <span data-ttu-id="875fd-138">El siguiente código de ejemplo muestra la implementación de un servicio básico de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que publica metadatos para el servicio mediante código.</span><span class="sxs-lookup"><span data-stu-id="875fd-138">The following code example shows the implementation of a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that publishes metadata for the service in code.</span></span>  
  
 [!code-csharp[htPublishMetadataCode#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#11)]
 [!code-vb[htPublishMetadataCode#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="875fd-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="875fd-139">See Also</span></span>  
 [<span data-ttu-id="875fd-140">Cómo hospedar un servicio WCF en una aplicación administrada</span><span class="sxs-lookup"><span data-stu-id="875fd-140">How to: Host a WCF Service in a Managed Application</span></span>](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)  
 [<span data-ttu-id="875fd-141">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="875fd-141">Self-Host</span></span>](../../../../docs/framework/wcf/samples/self-host.md)  
 [<span data-ttu-id="875fd-142">Información general de la arquitectura de metadatos</span><span class="sxs-lookup"><span data-stu-id="875fd-142">Metadata Architecture Overview</span></span>](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)  
 [<span data-ttu-id="875fd-143">Utilización de los metadatos</span><span class="sxs-lookup"><span data-stu-id="875fd-143">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [<span data-ttu-id="875fd-144">Publicación de metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="875fd-144">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
