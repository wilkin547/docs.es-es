---
title: "puntos de conexión: direcciones, enlaces y contratos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: af82cb934570b371d332c0e08ebc9b2338d0c0d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="57c7b-102">puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="57c7b-102">Endpoints: Addresses, Bindings, and Contracts</span></span>
<span data-ttu-id="57c7b-103">Toda la comunicación con un [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] servicio se produce a través de la *extremos* del servicio.</span><span class="sxs-lookup"><span data-stu-id="57c7b-103">All communication with a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="57c7b-104">Los extremos proporcionan acceso a los clientes a la funcionalidad que ofrece un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57c7b-104">Endpoints provide clients access to the functionality offered by a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="57c7b-105">Cada punto de conexión está compuesto de cuatro propiedades:</span><span class="sxs-lookup"><span data-stu-id="57c7b-105">Each endpoint consists of four properties:</span></span>  
  
-   <span data-ttu-id="57c7b-106">Una dirección que indica dónde se puede encontrar el extremo.</span><span class="sxs-lookup"><span data-stu-id="57c7b-106">An address that indicates where the endpoint can be found.</span></span>  
  
-   <span data-ttu-id="57c7b-107">Un enlace que especifica cómo un se puede comunicar un cliente con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="57c7b-107">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
-   <span data-ttu-id="57c7b-108">Un contrato que identifica las operaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="57c7b-108">A contract that identifies the operations available.</span></span>  
  
-   <span data-ttu-id="57c7b-109">Un conjunto de comportamientos que especifican detalles de implementación local del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="57c7b-109">A set of behaviors that specify local implementation details of the endpoint.</span></span>  
  
 <span data-ttu-id="57c7b-110">En este tema se describe esta estructura de extremo y se explica cómo se representa en el modelo de objetos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57c7b-110">This topic discusses this endpoint structure and explains how it is represented in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] object model.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="57c7b-111">Estructura de un punto de conexión</span><span class="sxs-lookup"><span data-stu-id="57c7b-111">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="57c7b-112">Cada punto de conexión está compuesto de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="57c7b-112">Each endpoint consists of the following:</span></span>  
  
-   <span data-ttu-id="57c7b-113">Dirección: la dirección identifica únicamente el punto de conexión e indica a los consumidores potenciales del servicio dónde se ubica éste.</span><span class="sxs-lookup"><span data-stu-id="57c7b-113">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="57c7b-114">Está representado en el modelo de objetos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] por la clase <xref:System.ServiceModel.EndpointAddress>.</span><span class="sxs-lookup"><span data-stu-id="57c7b-114">It is represented in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="57c7b-115">Una clase <xref:System.ServiceModel.EndpointAddress> contiene:</span><span class="sxs-lookup"><span data-stu-id="57c7b-115">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>  
  
    -   <span data-ttu-id="57c7b-116">Una propiedad <xref:System.ServiceModel.EndpointAddress.Uri%2A>, que representa la dirección del servicio.</span><span class="sxs-lookup"><span data-stu-id="57c7b-116">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>  
  
    -   <span data-ttu-id="57c7b-117">Una propiedad <xref:System.ServiceModel.EndpointAddress.Identity%2A>, que representa la identidad de seguridad del servicio y una colección de encabezados de mensaje opcionales.</span><span class="sxs-lookup"><span data-stu-id="57c7b-117">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="57c7b-118">Los encabezados de mensaje opcionales se utilizan para proporcionar información de direccionamiento adicional y más detallada para identificar o interactuar con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="57c7b-118">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>  
  
     [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="57c7b-119">[Al especificar una dirección de punto de conexión](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="57c7b-119"> [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
-   <span data-ttu-id="57c7b-120">Enlace: el enlace especifica cómo comunicarse con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="57c7b-120">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="57c7b-121">Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="57c7b-121">This includes:</span></span>  
  
    -   <span data-ttu-id="57c7b-122">El protocolo de transporte que se ha de utilizar (por ejemplo, TCP o HTTP).</span><span class="sxs-lookup"><span data-stu-id="57c7b-122">The transport protocol to use (for example, TCP or HTTP).</span></span>  
  
    -   <span data-ttu-id="57c7b-123">La codificación que se ha de utilizar para los mensajes (por ejemplo, texto o binario).</span><span class="sxs-lookup"><span data-stu-id="57c7b-123">The encoding to use for the messages (for example, text or binary).</span></span>  
  
    -   <span data-ttu-id="57c7b-124">Los requisitos de seguridad necesarios (por ejemplo, SSL o seguridad de mensaje SOAP).</span><span class="sxs-lookup"><span data-stu-id="57c7b-124">The necessary security requirements (for example, SSL or SOAP message security).</span></span>  
  
     [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="57c7b-125">[Información general de enlaces de WCF](../../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="57c7b-125"> [WCF Bindings Overview](../../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="57c7b-126">Un enlace se representa en el modelo de objetos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante la clase base abstracta <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="57c7b-126">A binding is represented in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="57c7b-127">Para la mayoría de los escenarios, los usuarios pueden utilizar uno de los enlaces proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="57c7b-127">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="57c7b-128">Para obtener más información, consulte [enlaces proporcionados](../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="57c7b-128">For more information, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
-   <span data-ttu-id="57c7b-129">Contratos: el contrato describe qué funcionalidad expone el punto de conexión al cliente.</span><span class="sxs-lookup"><span data-stu-id="57c7b-129">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="57c7b-130">Un contrato especifica:</span><span class="sxs-lookup"><span data-stu-id="57c7b-130">A contract specifies:</span></span>  
  
    -   <span data-ttu-id="57c7b-131">Qué operaciones puede llamar un cliente.</span><span class="sxs-lookup"><span data-stu-id="57c7b-131">What operations can be called by a client.</span></span>  
  
    -   <span data-ttu-id="57c7b-132">La forma del mensaje.</span><span class="sxs-lookup"><span data-stu-id="57c7b-132">The form of the message.</span></span>  
  
    -   <span data-ttu-id="57c7b-133">El tipo de parámetros de entrada o datos requeridos para llamar a la operación.</span><span class="sxs-lookup"><span data-stu-id="57c7b-133">The type of input parameters or data required to call the operation.</span></span>  
  
    -   <span data-ttu-id="57c7b-134">Qué tipo de mensaje de procesamiento respuesta puede esperar el cliente.</span><span class="sxs-lookup"><span data-stu-id="57c7b-134">What type of processing or response message the client can expect.</span></span>  
  
     <span data-ttu-id="57c7b-135">Para obtener más información acerca de cómo definir un contrato, vea [diseñar contratos de servicio](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="57c7b-135">For more information about defining a contract, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
-   <span data-ttu-id="57c7b-136">Comportamientos: puede utilizar los comportamientos de punto de conexión para personalizar el comportamiento local del punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="57c7b-136">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="57c7b-137">Comportamientos de extremo logran esto participando en el proceso de creación una [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="57c7b-137">Endpoint behaviors achieve this by participating in the process of building a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]runtime.</span></span> <span data-ttu-id="57c7b-138">Un ejemplo de un comportamiento de extremo es la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, que permite especificar una dirección de escucha diferente que la dirección SOAP o la dirección del Lenguaje de descripción de servicios Web (WSDL).</span><span class="sxs-lookup"><span data-stu-id="57c7b-138">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="57c7b-139">[ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span><span class="sxs-lookup"><span data-stu-id="57c7b-139"> [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span></span>  
  
## <a name="defining-endpoints"></a><span data-ttu-id="57c7b-140">Definición de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="57c7b-140">Defining Endpoints</span></span>  
 <span data-ttu-id="57c7b-141">Puede especificar el punto de conexión de un servicio de manera imperativa mediante código o de manera declarativa mediante configuración.</span><span class="sxs-lookup"><span data-stu-id="57c7b-141">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="57c7b-142">[Cómo: crear un extremo de servicio en configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) y [Cómo: crear un extremo de servicio en el código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="57c7b-142"> [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57c7b-143">En esta sección</span><span class="sxs-lookup"><span data-stu-id="57c7b-143">In This Section</span></span>  
 <span data-ttu-id="57c7b-144">En esta sección se explica el propósito de los enlaces, extremos y direcciones; se muestra cómo configurar un enlace y un extremo; y cómo utilizar el comportamiento `ClientVia` y la propiedad `ListenUri`.</span><span class="sxs-lookup"><span data-stu-id="57c7b-144">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>  
  
 [<span data-ttu-id="57c7b-145">Direcciones</span><span class="sxs-lookup"><span data-stu-id="57c7b-145">Addresses</span></span>](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 <span data-ttu-id="57c7b-146">Describe cómo se direccionan los extremos en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57c7b-146">Describes how endpoints are addressed in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="57c7b-147">Enlaces</span><span class="sxs-lookup"><span data-stu-id="57c7b-147">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 <span data-ttu-id="57c7b-148">Describe cómo se utilizan los enlaces para especificar el transporte, codificación y detalles protocolares requeridos para que los clientes y servicios se comuniquen entre sí.</span><span class="sxs-lookup"><span data-stu-id="57c7b-148">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>  
  
 [<span data-ttu-id="57c7b-149">Contratos</span><span class="sxs-lookup"><span data-stu-id="57c7b-149">Contracts</span></span>](../../../../docs/framework/wcf/feature-details/contracts.md)  
 <span data-ttu-id="57c7b-150">Describe cómo los contratos definen los métodos de un servicio.</span><span class="sxs-lookup"><span data-stu-id="57c7b-150">Describes how contracts define the methods of a service.</span></span>  
  
 [<span data-ttu-id="57c7b-151">Creación de un punto de conexión de servicio en configuración</span><span class="sxs-lookup"><span data-stu-id="57c7b-151">How to: Create a Service Endpoint in Configuration</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="57c7b-152">Describe cómo crear un punto de conexión de servicio mediante configuración</span><span class="sxs-lookup"><span data-stu-id="57c7b-152">Describes how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="57c7b-153">Creación de un punto de conexión de servicio en código</span><span class="sxs-lookup"><span data-stu-id="57c7b-153">How to: Create a Service Endpoint in Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="57c7b-154">Describe cómo crear un punto de conexión de servicio mediante código.</span><span class="sxs-lookup"><span data-stu-id="57c7b-154">Describes how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="57c7b-155">Uso de Svcutil.exe para validar el código del servicio compilado</span><span class="sxs-lookup"><span data-stu-id="57c7b-155">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 <span data-ttu-id="57c7b-156">Describe cómo detectar errores en las configuraciones y las implementaciones del servicio sin hospedar el servicio utilizando la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="57c7b-156">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57c7b-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="57c7b-157">See Also</span></span>  
 [<span data-ttu-id="57c7b-158">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="57c7b-158">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
 [<span data-ttu-id="57c7b-159">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="57c7b-159">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
