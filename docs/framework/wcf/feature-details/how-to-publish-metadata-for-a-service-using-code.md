---
description: 'Más información acerca de cómo: publicar metadatos para un servicio mediante código'
title: Procedimiento para publicar metadatos para un servicio mediante código
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 51407e6d-4d87-42d5-be7c-9887b8652006
ms.openlocfilehash: 94939c77b1c66643b0cc378516479e35c41aefbb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793693"
---
# <a name="how-to-publish-metadata-for-a-service-using-code"></a><span data-ttu-id="b787c-103">Procedimiento para publicar metadatos para un servicio mediante código</span><span class="sxs-lookup"><span data-stu-id="b787c-103">How to: Publish Metadata for a Service Using Code</span></span>

<span data-ttu-id="b787c-104">Este es uno de los dos temas de procedimientos que tratan la publicación de metadatos para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="b787c-104">This is one of two how-to topics that discuss publishing metadata for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="b787c-105">Hay dos maneras de especificar cómo debería publicar metadatos un servicio: mediante un archivo de configuración y mediante código.</span><span class="sxs-lookup"><span data-stu-id="b787c-105">There are two ways to specify how a service should publish metadata, using a configuration file and using code.</span></span> <span data-ttu-id="b787c-106">En este tema se muestra cómo publicar metadatos para un servicio mediante código.</span><span class="sxs-lookup"><span data-stu-id="b787c-106">This topic shows how to publish metadata for a service using a code.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="b787c-107">En este tema se muestra cómo publicar metadatos de forma no segura.</span><span class="sxs-lookup"><span data-stu-id="b787c-107">This topic shows how to publish metadata in an unsecure manner.</span></span> <span data-ttu-id="b787c-108">Cualquier cliente puede recuperar los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="b787c-108">Any client can retrieve the metadata from the service.</span></span> <span data-ttu-id="b787c-109">Si el servicio necesita publicar los metadatos de forma segura.</span><span class="sxs-lookup"><span data-stu-id="b787c-109">If you require your service to publish metadata in a secure manner.</span></span> <span data-ttu-id="b787c-110">consulte [punto de conexión de metadatos seguro personalizado](../samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="b787c-110">see [Custom Secure Metadata Endpoint](../samples/custom-secure-metadata-endpoint.md).</span></span>  
  
 <span data-ttu-id="b787c-111">Para obtener más información sobre la publicación de metadatos en un archivo de configuración, vea [Cómo: publicar metadatos para un servicio mediante un archivo de configuración](how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="b787c-111">For more information about publishing metadata in a configuration file, see [How to: Publish Metadata for a Service Using a Configuration File](how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span> <span data-ttu-id="b787c-112">La publicación de metadatos permite a los clientes recuperar los metadatos mediante una solicitud GET WS-Transfer o mediante una solicitud HTTP/GET usando la cadena de solicitud `?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="b787c-112">Publishing metadata allows clients to retrieve the metadata using a WS-Transfer GET request or an HTTP/GET request using the `?wsdl` query string.</span></span> <span data-ttu-id="b787c-113">Para asegurarse de que el código funciona, debe crear un servicio básico de WCF.</span><span class="sxs-lookup"><span data-stu-id="b787c-113">To be sure that the code is working you must create a basic WCF service.</span></span> <span data-ttu-id="b787c-114">En el código siguiente, se proporciona un servicio autohospedado básico.</span><span class="sxs-lookup"><span data-stu-id="b787c-114">A basic self-hosted service is provided in the following code.</span></span>  
  
 [!code-csharp[htPublishMetadataCode#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#0)]
 [!code-vb[htPublishMetadataCode#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#0)]  
  
### <a name="to-publish-metadata-in-code"></a><span data-ttu-id="b787c-115">Publicación de metadatos mediante código</span><span class="sxs-lookup"><span data-stu-id="b787c-115">To publish metadata in code</span></span>  
  
1. <span data-ttu-id="b787c-116">Dentro del método principal de una aplicación de consola, cree instancias de un objeto <xref:System.ServiceModel.ServiceHost> pasando el tipo de servicio y la dirección base.</span><span class="sxs-lookup"><span data-stu-id="b787c-116">Within the main method of a console application, instantiate a <xref:System.ServiceModel.ServiceHost> object by passing in the service type and the base address.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#1)]
     [!code-vb[htPublishMetadataCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#1)]  
  
2. <span data-ttu-id="b787c-117">Cree un bloque try justo debajo del código del paso 1, esto detecta cualquier excepción que se produzca mientras se está ejecutando el servicio.</span><span class="sxs-lookup"><span data-stu-id="b787c-117">Create a try block immediately below the code for step 1, this catches any exceptions that get thrown while the service is running.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#2)]
     [!code-vb[htPublishMetadataCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#2)]  
  
     [!code-csharp[htPublishMetadataCode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#3)]
     [!code-vb[htPublishMetadataCode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#3)]  
  
3. <span data-ttu-id="b787c-118">Compruebe si el host del servicio ya contiene un <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, si no, cree una nueva instancia de <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="b787c-118">Check to see whether the service host already contains a <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, if not, create a new <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#4)]
     [!code-vb[htPublishMetadataCode#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#4)]  
  
4. <span data-ttu-id="b787c-119">Establezca la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en `true.`.</span><span class="sxs-lookup"><span data-stu-id="b787c-119">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true.`</span></span>  
  
     [!code-csharp[htPublishMetadataCode#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#5)]
     [!code-vb[htPublishMetadataCode#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#5)]  
  
5. <span data-ttu-id="b787c-120">El <xref:System.ServiceModel.Description.ServiceMetadataBehavior> contiene una propiedad <xref:System.ServiceModel.Description.MetadataExporter>.</span><span class="sxs-lookup"><span data-stu-id="b787c-120">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior> contains a <xref:System.ServiceModel.Description.MetadataExporter> property.</span></span> <span data-ttu-id="b787c-121">El <xref:System.ServiceModel.Description.MetadataExporter> contiene una propiedad <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="b787c-121">The <xref:System.ServiceModel.Description.MetadataExporter> contains a <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property.</span></span> <span data-ttu-id="b787c-122">Establezca el valor de la propiedad <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> en <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>.</span><span class="sxs-lookup"><span data-stu-id="b787c-122">Set the value of the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>.</span></span> <span data-ttu-id="b787c-123">La propiedad <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> también se puede establecer en <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>.</span><span class="sxs-lookup"><span data-stu-id="b787c-123">The <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property can also be set to <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>.</span></span> <span data-ttu-id="b787c-124">Cuando se establece en, <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> el exportador de metadatos genera información de directivas con los metadatos que "se ajusta a WS-Policy 1,5.</span><span class="sxs-lookup"><span data-stu-id="b787c-124">When set to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> the metadata exporter generates policy information with the metadata that" conforms to WS-Policy 1.5.</span></span> <span data-ttu-id="b787c-125">Cuando se establece en <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>, el exportador de metadatos genera información de directivas conforme a la especificación WS-Policy 1.2.</span><span class="sxs-lookup"><span data-stu-id="b787c-125">When set to <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A> the metadata exporter generates policy information that conforms to WS-Policy 1.2.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#6)]
     [!code-vb[htPublishMetadataCode#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#6)]  
  
6. <span data-ttu-id="b787c-126">Agregue la instancia de <xref:System.ServiceModel.Description.ServiceMetadataBehavior> a la colección de comportamientos del host del servicio.</span><span class="sxs-lookup"><span data-stu-id="b787c-126">Add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance to the service host's behaviors collection.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#7)]
     [!code-vb[htPublishMetadataCode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#7)]  
  
7. <span data-ttu-id="b787c-127">Agregue el punto de conexión de intercambio de metadatos al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="b787c-127">Add the metadata exchange endpoint to the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#8)]
     [!code-vb[htPublishMetadataCode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#8)]  
  
8. <span data-ttu-id="b787c-128">Agregue un extremo de la aplicación al host de servicio.</span><span class="sxs-lookup"><span data-stu-id="b787c-128">Add an application endpoint to the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#9)]
     [!code-vb[htPublishMetadataCode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#9)]  
  
    > [!NOTE]
    > <span data-ttu-id="b787c-129">Si no agrega ningún punto de conexión al servicio, el tiempo de ejecución agregará los puntos de conexión predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b787c-129">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="b787c-130">En este ejemplo, dado que el servicio tiene un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> establecido en `true`, el servicio tiene habilitada la publicación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="b787c-130">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, the service has publishing metadata enabled.</span></span> <span data-ttu-id="b787c-131">Para obtener más información sobre los puntos de conexión predeterminados, vea [configuración simplificada](../simplified-configuration.md) y [configuración simplificada para servicios WCF](../samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="b787c-131">For more information about default endpoints, see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
9. <span data-ttu-id="b787c-132">Abra el host de servicio y espere las llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="b787c-132">Open the service host and wait for incoming calls.</span></span> <span data-ttu-id="b787c-133">Cuando el usuario presione Entrar, cierre el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="b787c-133">When the user presses ENTER, close the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#10)]
     [!code-vb[htPublishMetadataCode#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#10)]  
  
10. <span data-ttu-id="b787c-134">Compilación y ejecución de la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="b787c-134">Build and run the console application.</span></span>  
  
11. <span data-ttu-id="b787c-135">Use Internet Explorer para ir a la dirección base del servicio ( `http://localhost:8001/MetadataSample` en este ejemplo) y compruebe que la publicación de metadatos está activada.</span><span class="sxs-lookup"><span data-stu-id="b787c-135">Use Internet Explorer to browse to the base address of the service (`http://localhost:8001/MetadataSample` in this sample) and verify that the metadata publishing is turned on.</span></span> <span data-ttu-id="b787c-136">Debería ver una página web que dice "Servicio Simple" en la parte superior y, justo debajo, "Ha creado un servicio".</span><span class="sxs-lookup"><span data-stu-id="b787c-136">You should see a Web page displayed that says "Simple Service" at the top and immediately below "You have created a service."</span></span> <span data-ttu-id="b787c-137">Si no, un mensaje en la parte superior de la página resultante muestra: "La publicación de metadatos para este servicio está deshabilitad actualmente".</span><span class="sxs-lookup"><span data-stu-id="b787c-137">If not, a message at the top of the resulting page displays: "Metadata publishing for this service is currently disabled."</span></span>  
  
## <a name="example"></a><span data-ttu-id="b787c-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b787c-138">Example</span></span>  

 <span data-ttu-id="b787c-139">En el ejemplo de código siguiente se muestra la implementación de un servicio WCF básico que publica los metadatos para el servicio en el código.</span><span class="sxs-lookup"><span data-stu-id="b787c-139">The following code example shows the implementation of a basic WCF service that publishes metadata for the service in code.</span></span>  
  
 [!code-csharp[htPublishMetadataCode#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#11)]
 [!code-vb[htPublishMetadataCode#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="b787c-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="b787c-140">See also</span></span>

- [<span data-ttu-id="b787c-141">Procedimiento para hospedar un servicio WCF en una aplicación administrada</span><span class="sxs-lookup"><span data-stu-id="b787c-141">How to: Host a WCF Service in a Managed Application</span></span>](../how-to-host-a-wcf-service-in-a-managed-application.md)
- [<span data-ttu-id="b787c-142">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="b787c-142">Self-Host</span></span>](../samples/self-host.md)
- [<span data-ttu-id="b787c-143">Información general de la arquitectura de metadatos</span><span class="sxs-lookup"><span data-stu-id="b787c-143">Metadata Architecture Overview</span></span>](metadata-architecture-overview.md)
- [<span data-ttu-id="b787c-144">Utilización de los metadatos</span><span class="sxs-lookup"><span data-stu-id="b787c-144">Using Metadata</span></span>](using-metadata.md)
- [<span data-ttu-id="b787c-145">Procedimiento para publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="b787c-145">How to: Publish Metadata for a Service Using a Configuration File</span></span>](how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
