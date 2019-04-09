---
title: 'Puntos de conexión: direcciones, enlaces y contratos'
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: 3e78e7cf0c5acde53d7ee23294fd52134414e860
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207531"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="ab0f5-102">Puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="ab0f5-102">Endpoints: Addresses, Bindings, and Contracts</span></span>
<span data-ttu-id="ab0f5-103">Toda la comunicación con un servicio de Windows Communication Foundation (WCF) se produce a través de la *extremos* del servicio.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="ab0f5-104">Los extremos proporcionan a los clientes acceso a la funcionalidad que ofrece un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-104">Endpoints provide clients access to the functionality offered by a WCF service.</span></span>  
  
 <span data-ttu-id="ab0f5-105">Cada punto de conexión está compuesto de cuatro propiedades:</span><span class="sxs-lookup"><span data-stu-id="ab0f5-105">Each endpoint consists of four properties:</span></span>  
  
-   <span data-ttu-id="ab0f5-106">Una dirección que indica dónde se puede encontrar el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-106">An address that indicates where the endpoint can be found.</span></span>  
  
-   <span data-ttu-id="ab0f5-107">Un enlace que especifica cómo un se puede comunicar un cliente con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-107">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
-   <span data-ttu-id="ab0f5-108">Un contrato que identifica las operaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-108">A contract that identifies the operations available.</span></span>  
  
-   <span data-ttu-id="ab0f5-109">Un conjunto de comportamientos que especifican detalles de implementación local del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-109">A set of behaviors that specify local implementation details of the endpoint.</span></span>  
  
 <span data-ttu-id="ab0f5-110">En este tema se describe esta estructura de punto de conexión y se explica cómo se representa en el modelo de objetos WCF.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-110">This topic discusses this endpoint structure and explains how it is represented in the WCF object model.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="ab0f5-111">Estructura de un extremo</span><span class="sxs-lookup"><span data-stu-id="ab0f5-111">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="ab0f5-112">Cada punto de conexión está compuesto de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ab0f5-112">Each endpoint consists of the following:</span></span>  
  
-   <span data-ttu-id="ab0f5-113">Dirección: La dirección identifica el punto de conexión y le indica a posibles consumidores del servicio donde se encuentra.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-113">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="ab0f5-114">Se representa en el modelo de objetos WCF mediante el <xref:System.ServiceModel.EndpointAddress> clase.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-114">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="ab0f5-115">Una clase <xref:System.ServiceModel.EndpointAddress> contiene:</span><span class="sxs-lookup"><span data-stu-id="ab0f5-115">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>  
  
    -   <span data-ttu-id="ab0f5-116">Una propiedad <xref:System.ServiceModel.EndpointAddress.Uri%2A>, que representa la dirección del servicio.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-116">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>  
  
    -   <span data-ttu-id="ab0f5-117">Una propiedad <xref:System.ServiceModel.EndpointAddress.Identity%2A>, que representa la identidad de seguridad del servicio y una colección de encabezados de mensaje opcionales.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-117">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="ab0f5-118">Los encabezados de mensaje opcionales se utilizan para proporcionar información de direccionamiento adicional y más detallada para identificar o interactuar con el extremo.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-118">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>  
  
     <span data-ttu-id="ab0f5-119">Para obtener más información, consulte [especificando una dirección de extremo](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="ab0f5-119">For more information, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
-   <span data-ttu-id="ab0f5-120">Enlace: El enlace especifica cómo comunicarse con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-120">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="ab0f5-121">Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="ab0f5-121">This includes:</span></span>  
  
    -   <span data-ttu-id="ab0f5-122">El protocolo de transporte que se ha de utilizar (por ejemplo, TCP o HTTP).</span><span class="sxs-lookup"><span data-stu-id="ab0f5-122">The transport protocol to use (for example, TCP or HTTP).</span></span>  
  
    -   <span data-ttu-id="ab0f5-123">La codificación que se ha de utilizar para los mensajes (por ejemplo, texto o binario).</span><span class="sxs-lookup"><span data-stu-id="ab0f5-123">The encoding to use for the messages (for example, text or binary).</span></span>  
  
    -   <span data-ttu-id="ab0f5-124">Los requisitos de seguridad necesarios (por ejemplo, SSL o seguridad de mensaje SOAP).</span><span class="sxs-lookup"><span data-stu-id="ab0f5-124">The necessary security requirements (for example, SSL or SOAP message security).</span></span>  
  
     <span data-ttu-id="ab0f5-125">Para obtener más información, consulte [información general sobre los enlaces de WCF](../../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ab0f5-125">For more information, see [WCF Bindings Overview](../../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="ab0f5-126">Un enlace se representa en el modelo de objetos WCF mediante la clase base abstracta <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-126">A binding is represented in the WCF object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="ab0f5-127">Para la mayoría de los escenarios, los usuarios pueden utilizar uno de los enlaces proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-127">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="ab0f5-128">Para obtener más información, consulte [System-provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="ab0f5-128">For more information, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
-   <span data-ttu-id="ab0f5-129">Contratos: El contrato describe qué funcionalidad expone el punto de conexión al cliente.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-129">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="ab0f5-130">Un contrato especifica:</span><span class="sxs-lookup"><span data-stu-id="ab0f5-130">A contract specifies:</span></span>  
  
    -   <span data-ttu-id="ab0f5-131">Qué operaciones puede llamar un cliente.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-131">What operations can be called by a client.</span></span>  
  
    -   <span data-ttu-id="ab0f5-132">La forma del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-132">The form of the message.</span></span>  
  
    -   <span data-ttu-id="ab0f5-133">El tipo de parámetros de entrada o datos requeridos para llamar a la operación.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-133">The type of input parameters or data required to call the operation.</span></span>  
  
    -   <span data-ttu-id="ab0f5-134">Qué tipo de mensaje de procesamiento respuesta puede esperar el cliente.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-134">What type of processing or response message the client can expect.</span></span>  
  
     <span data-ttu-id="ab0f5-135">Para obtener más información acerca de cómo definir un contrato, vea [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="ab0f5-135">For more information about defining a contract, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
-   <span data-ttu-id="ab0f5-136">Comportamientos: Puede utilizar los comportamientos de extremo para personalizar el comportamiento del extremo del servicio local.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-136">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="ab0f5-137">Para ello, los comportamientos de extremo que participan en el proceso de creación de un WCFruntime.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-137">Endpoint behaviors achieve this by participating in the process of building a WCFruntime.</span></span> <span data-ttu-id="ab0f5-138">Un ejemplo de un comportamiento de punto de conexión es la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, que permite especificar una dirección de escucha diferente que la dirección SOAP o la dirección del Lenguaje de descripción de servicios Web (WSDL).</span><span class="sxs-lookup"><span data-stu-id="ab0f5-138">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> <span data-ttu-id="ab0f5-139">Para obtener más información, consulte [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span><span class="sxs-lookup"><span data-stu-id="ab0f5-139">For more information, see [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span></span>  
  
## <a name="defining-endpoints"></a><span data-ttu-id="ab0f5-140">Definición de extremos</span><span class="sxs-lookup"><span data-stu-id="ab0f5-140">Defining Endpoints</span></span>  
 <span data-ttu-id="ab0f5-141">Puede especificar el extremo de un servicio de manera imperativa mediante código o de manera declarativa mediante configuración.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-141">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="ab0f5-142">Para obtener más información, vea [Cómo: Crear un punto de conexión de servicio en la configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) y [Cómo: Crear un punto de conexión de servicio en código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="ab0f5-142">For more information, see [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab0f5-143">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ab0f5-143">In This Section</span></span>  
 <span data-ttu-id="ab0f5-144">En esta sección se explica el propósito de los enlaces, extremos y direcciones; se muestra cómo configurar un enlace y un extremo; y cómo utilizar el comportamiento `ClientVia` y la propiedad `ListenUri`.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-144">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>  
  
 [<span data-ttu-id="ab0f5-145">Direcciones</span><span class="sxs-lookup"><span data-stu-id="ab0f5-145">Addresses</span></span>](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 <span data-ttu-id="ab0f5-146">Describe cómo se direccionan los puntos de conexión en WCF.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-146">Describes how endpoints are addressed in WCF.</span></span>  
  
 [<span data-ttu-id="ab0f5-147">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ab0f5-147">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 <span data-ttu-id="ab0f5-148">Describe cómo se utilizan los enlaces para especificar el transporte, codificación y detalles protocolares requeridos para que los clientes y servicios se comuniquen entre sí.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-148">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>  
  
 [<span data-ttu-id="ab0f5-149">Contratos</span><span class="sxs-lookup"><span data-stu-id="ab0f5-149">Contracts</span></span>](../../../../docs/framework/wcf/feature-details/contracts.md)  
 <span data-ttu-id="ab0f5-150">Describe cómo los contratos definen los métodos de un servicio.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-150">Describes how contracts define the methods of a service.</span></span>  
  
 [<span data-ttu-id="ab0f5-151">Filtrar para crear un punto de conexión de servicio en la configuración</span><span class="sxs-lookup"><span data-stu-id="ab0f5-151">How to: Create a Service Endpoint in Configuration</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="ab0f5-152">Describe cómo crear un punto de conexión de servicio mediante configuración</span><span class="sxs-lookup"><span data-stu-id="ab0f5-152">Describes how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="ab0f5-153">Filtrar para crear un punto de conexión de servicio mediante código</span><span class="sxs-lookup"><span data-stu-id="ab0f5-153">How to: Create a Service Endpoint in Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="ab0f5-154">Describe cómo crear un extremo de servicio mediante código.</span><span class="sxs-lookup"><span data-stu-id="ab0f5-154">Describes how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="ab0f5-155">Filtrar para usar Svcutil.exe para validar el código del servicio compilado</span><span class="sxs-lookup"><span data-stu-id="ab0f5-155">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 <span data-ttu-id="ab0f5-156">Describe cómo detectar errores en las implementaciones de servicio y configuraciones sin hospedar el servicio mediante el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="ab0f5-156">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab0f5-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab0f5-157">See also</span></span>

- [<span data-ttu-id="ab0f5-158">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="ab0f5-158">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)
- [<span data-ttu-id="ab0f5-159">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="ab0f5-159">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
