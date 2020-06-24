---
title: 'Puntos de conexión: direcciones, enlaces y contratos'
description: Obtenga información acerca de cómo se produce toda comunicación con un servicio WCF a través de los puntos de conexión de servicio, que proporcionan a los clientes acceso a la funcionalidad que ofrece el servicio.
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: ce0874bfed716716b6fd1801b35a4266095cd752
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247317"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="bef42-103">Puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="bef42-103">Endpoints: Addresses, Bindings, and Contracts</span></span>

<span data-ttu-id="bef42-104">Toda la comunicación con un servicio de Windows Communication Foundation (WCF) se produce a través de los *extremos* del servicio.</span><span class="sxs-lookup"><span data-stu-id="bef42-104">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="bef42-105">Los extremos proporcionan a los clientes acceso a la funcionalidad que ofrece un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="bef42-105">Endpoints provide clients access to the functionality offered by a WCF service.</span></span>

<span data-ttu-id="bef42-106">Cada punto de conexión está compuesto de cuatro propiedades:</span><span class="sxs-lookup"><span data-stu-id="bef42-106">Each endpoint consists of four properties:</span></span>

- <span data-ttu-id="bef42-107">Una dirección que indica dónde se puede encontrar el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bef42-107">An address that indicates where the endpoint can be found.</span></span>

- <span data-ttu-id="bef42-108">Un enlace que especifica cómo un se puede comunicar un cliente con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bef42-108">A binding that specifies how a client can communicate with the endpoint.</span></span>

- <span data-ttu-id="bef42-109">Un contrato que identifica las operaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="bef42-109">A contract that identifies the operations available.</span></span>

- <span data-ttu-id="bef42-110">Un conjunto de comportamientos que especifican detalles de implementación local del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bef42-110">A set of behaviors that specify local implementation details of the endpoint.</span></span>

<span data-ttu-id="bef42-111">En este tema se describe esta estructura de extremos y se explica cómo se representa en el modelo de objetos WCF.</span><span class="sxs-lookup"><span data-stu-id="bef42-111">This topic discusses this endpoint structure and explains how it is represented in the WCF object model.</span></span>

## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="bef42-112">Estructura de un extremo</span><span class="sxs-lookup"><span data-stu-id="bef42-112">The Structure of an Endpoint</span></span>

<span data-ttu-id="bef42-113">Cada punto de conexión está compuesto de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bef42-113">Each endpoint consists of the following:</span></span>

- <span data-ttu-id="bef42-114">Dirección: la dirección identifica únicamente el punto de conexión e indica a los consumidores potenciales del servicio dónde se ubica éste.</span><span class="sxs-lookup"><span data-stu-id="bef42-114">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="bef42-115">Se representa en el modelo de objetos WCF mediante la <xref:System.ServiceModel.EndpointAddress> clase.</span><span class="sxs-lookup"><span data-stu-id="bef42-115">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="bef42-116">Una clase <xref:System.ServiceModel.EndpointAddress> contiene:</span><span class="sxs-lookup"><span data-stu-id="bef42-116">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>

  - <span data-ttu-id="bef42-117">Una propiedad <xref:System.ServiceModel.EndpointAddress.Uri%2A>, que representa la dirección del servicio.</span><span class="sxs-lookup"><span data-stu-id="bef42-117">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>

  - <span data-ttu-id="bef42-118">Una propiedad <xref:System.ServiceModel.EndpointAddress.Identity%2A>, que representa la identidad de seguridad del servicio y una colección de encabezados de mensaje opcionales.</span><span class="sxs-lookup"><span data-stu-id="bef42-118">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="bef42-119">Los encabezados de mensaje opcionales se utilizan para proporcionar información de direccionamiento adicional y más detallada para identificar o interactuar con el extremo.</span><span class="sxs-lookup"><span data-stu-id="bef42-119">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>

  <span data-ttu-id="bef42-120">Para obtener más información, vea [especificar una dirección de extremo](../specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="bef42-120">For more information, see [Specifying an Endpoint Address](../specifying-an-endpoint-address.md).</span></span>

- <span data-ttu-id="bef42-121">Enlace: el enlace especifica cómo comunicarse con el extremo.</span><span class="sxs-lookup"><span data-stu-id="bef42-121">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="bef42-122">Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="bef42-122">This includes:</span></span>

  - <span data-ttu-id="bef42-123">El protocolo de transporte que se ha de utilizar (por ejemplo, TCP o HTTP).</span><span class="sxs-lookup"><span data-stu-id="bef42-123">The transport protocol to use (for example, TCP or HTTP).</span></span>

  - <span data-ttu-id="bef42-124">La codificación que se ha de utilizar para los mensajes (por ejemplo, texto o binario).</span><span class="sxs-lookup"><span data-stu-id="bef42-124">The encoding to use for the messages (for example, text or binary).</span></span>

  - <span data-ttu-id="bef42-125">Los requisitos de seguridad necesarios (por ejemplo, SSL o seguridad de mensaje SOAP).</span><span class="sxs-lookup"><span data-stu-id="bef42-125">The necessary security requirements (for example, SSL or SOAP message security).</span></span>

  <span data-ttu-id="bef42-126">Para obtener más información, vea [información general sobre los enlaces de WCF](../bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bef42-126">For more information, see [WCF Bindings Overview](../bindings-overview.md).</span></span> <span data-ttu-id="bef42-127">La clase base abstracta representa un enlace en el modelo de objetos de WCF <xref:System.ServiceModel.Channels.Binding> .</span><span class="sxs-lookup"><span data-stu-id="bef42-127">A binding is represented in the WCF object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="bef42-128">Para la mayoría de los escenarios, los usuarios pueden utilizar uno de los enlaces proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="bef42-128">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="bef42-129">Para obtener más información, vea [enlaces proporcionados por el sistema](../system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="bef42-129">For more information, see [System-Provided Bindings](../system-provided-bindings.md).</span></span>

- <span data-ttu-id="bef42-130">Contratos: el contrato describe qué funcionalidad expone el punto de conexión al cliente.</span><span class="sxs-lookup"><span data-stu-id="bef42-130">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="bef42-131">Un contrato especifica:</span><span class="sxs-lookup"><span data-stu-id="bef42-131">A contract specifies:</span></span>

  - <span data-ttu-id="bef42-132">Qué operaciones puede llamar un cliente.</span><span class="sxs-lookup"><span data-stu-id="bef42-132">What operations can be called by a client.</span></span>

  - <span data-ttu-id="bef42-133">La forma del mensaje.</span><span class="sxs-lookup"><span data-stu-id="bef42-133">The form of the message.</span></span>

  - <span data-ttu-id="bef42-134">El tipo de parámetros de entrada o datos requeridos para llamar a la operación.</span><span class="sxs-lookup"><span data-stu-id="bef42-134">The type of input parameters or data required to call the operation.</span></span>

  - <span data-ttu-id="bef42-135">Qué tipo de mensaje de procesamiento respuesta puede esperar el cliente.</span><span class="sxs-lookup"><span data-stu-id="bef42-135">What type of processing or response message the client can expect.</span></span>

  <span data-ttu-id="bef42-136">Para obtener más información sobre cómo definir un contrato, consulte [diseño de contratos de servicio](../designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="bef42-136">For more information about defining a contract, see [Designing Service Contracts](../designing-service-contracts.md).</span></span>

- <span data-ttu-id="bef42-137">Comportamientos: puede utilizar los comportamientos de punto de conexión para personalizar el comportamiento local del punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="bef42-137">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="bef42-138">Los comportamientos del punto de conexión logran esto participando en el proceso de compilación de un tiempo de ejecución de WCF.</span><span class="sxs-lookup"><span data-stu-id="bef42-138">Endpoint behaviors achieve this by participating in the process of building a WCF runtime.</span></span> <span data-ttu-id="bef42-139">Un ejemplo de un comportamiento de punto de conexión es la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, que permite especificar una dirección de escucha diferente que la dirección SOAP o la dirección del Lenguaje de descripción de servicios Web (WSDL).</span><span class="sxs-lookup"><span data-stu-id="bef42-139">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> <span data-ttu-id="bef42-140">Para obtener más información, vea [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md).</span><span class="sxs-lookup"><span data-stu-id="bef42-140">For more information, see [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md).</span></span>

## <a name="defining-endpoints"></a><span data-ttu-id="bef42-141">Definición de extremos</span><span class="sxs-lookup"><span data-stu-id="bef42-141">Defining Endpoints</span></span>

<span data-ttu-id="bef42-142">Puede especificar el extremo de un servicio de manera imperativa mediante código o de manera declarativa mediante configuración.</span><span class="sxs-lookup"><span data-stu-id="bef42-142">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="bef42-143">Para obtener más información, vea [Cómo: crear un punto de conexión de servicio en la configuración](how-to-create-a-service-endpoint-in-configuration.md) y [Cómo: crear un punto de conexión de servicio en el código](how-to-create-a-service-endpoint-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="bef42-143">For more information, see [How to: Create a Service Endpoint in Configuration](how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](how-to-create-a-service-endpoint-in-code.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bef42-144">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bef42-144">In This Section</span></span>

<span data-ttu-id="bef42-145">En esta sección se explica el propósito de los enlaces, extremos y direcciones; se muestra cómo configurar un enlace y un extremo; y cómo utilizar el comportamiento `ClientVia` y la propiedad `ListenUri`.</span><span class="sxs-lookup"><span data-stu-id="bef42-145">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>

<span data-ttu-id="bef42-146">[Corrige](endpoint-addresses.md)</span><span class="sxs-lookup"><span data-stu-id="bef42-146">[Addresses](endpoint-addresses.md)</span></span>\
<span data-ttu-id="bef42-147">Describe cómo se abordan los extremos en WCF.</span><span class="sxs-lookup"><span data-stu-id="bef42-147">Describes how endpoints are addressed in WCF.</span></span>

<span data-ttu-id="bef42-148">[Enlaces](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="bef42-148">[Bindings](bindings.md)</span></span>\
<span data-ttu-id="bef42-149">Describe cómo se utilizan los enlaces para especificar el transporte, codificación y detalles protocolares requeridos para que los clientes y servicios se comuniquen entre sí.</span><span class="sxs-lookup"><span data-stu-id="bef42-149">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>

<span data-ttu-id="bef42-150">[Trata](contracts.md)</span><span class="sxs-lookup"><span data-stu-id="bef42-150">[Contracts](contracts.md)</span></span>\
<span data-ttu-id="bef42-151">Describe cómo los contratos definen los métodos de un servicio.</span><span class="sxs-lookup"><span data-stu-id="bef42-151">Describes how contracts define the methods of a service.</span></span>

<span data-ttu-id="bef42-152">[Cómo: crear un punto de conexión de servicio en la configuración](how-to-create-a-service-endpoint-in-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="bef42-152">[How to: Create a Service Endpoint in Configuration](how-to-create-a-service-endpoint-in-configuration.md)</span></span>\
<span data-ttu-id="bef42-153">Describe cómo crear un punto de conexión de servicio mediante configuración</span><span class="sxs-lookup"><span data-stu-id="bef42-153">Describes how to create a service endpoint in configuration.</span></span>

<span data-ttu-id="bef42-154">[Cómo: crear un punto de conexión de servicio en el código](how-to-create-a-service-endpoint-in-code.md)</span><span class="sxs-lookup"><span data-stu-id="bef42-154">[How to: Create a Service Endpoint in Code](how-to-create-a-service-endpoint-in-code.md)</span></span>\
<span data-ttu-id="bef42-155">Describe cómo crear un extremo de servicio mediante código.</span><span class="sxs-lookup"><span data-stu-id="bef42-155">Describes how to create a service endpoint in code.</span></span>

<span data-ttu-id="bef42-156">[Cómo: usar Svcutil.exe para validar el código de servicio compilado](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)</span><span class="sxs-lookup"><span data-stu-id="bef42-156">[How to: Use Svcutil.exe to Validate Compiled Service Code](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)</span></span>\
<span data-ttu-id="bef42-157">Describe cómo detectar errores en las implementaciones de servicio y las configuraciones sin hospedar el servicio mediante la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="bef42-157">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bef42-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="bef42-158">See also</span></span>

- [<span data-ttu-id="bef42-159">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="bef42-159">Configuring Services</span></span>](../configuring-services.md)
- [<span data-ttu-id="bef42-160">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="bef42-160">Extending Bindings</span></span>](../extending/extending-bindings.md)
