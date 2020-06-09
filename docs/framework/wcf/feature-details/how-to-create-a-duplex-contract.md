---
title: Procedimiento para crear un contrato dúplex
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
ms.openlocfilehash: e5b6c7eecce08a23490b6ab1991e4561d9462469
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598988"
---
# <a name="how-to-create-a-duplex-contract"></a><span data-ttu-id="413f3-102">Procedimiento para crear un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="413f3-102">How to: Create a Duplex Contract</span></span>
<span data-ttu-id="413f3-103">En este tema se muestran los pasos básicos para crear métodos que utilicen un contrato dúplex (bidireccional).</span><span class="sxs-lookup"><span data-stu-id="413f3-103">This topic shows the basic steps to create methods that use a duplex (two-way) contract.</span></span> <span data-ttu-id="413f3-104">Un contrato dúplex permite a los clientes y servidores comunicarse entre sí independientemente de manera que cada uno puede iniciar llamadas al otro.</span><span class="sxs-lookup"><span data-stu-id="413f3-104">A duplex contract allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="413f3-105">El contrato dúplex es uno de tres patrones de mensajes disponibles para los servicios Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="413f3-105">The duplex contract is one of three message patterns available to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="413f3-106">Los otros dos patrones de mensaje son unidireccionales y de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="413f3-106">The other two message patterns are one-way and request-reply.</span></span> <span data-ttu-id="413f3-107">Un contrato dúplex consta de dos contratos unidireccionales entre el cliente y el servidor y no requiere que se pongan en correlación las llamadas al método.</span><span class="sxs-lookup"><span data-stu-id="413f3-107">A duplex contract consists of two one-way contracts between the client and the server and does not require that the method calls be correlated.</span></span> <span data-ttu-id="413f3-108">Use este tipo de contrato cuando el servicio debe consultar al cliente para obtener más información o provocar explícitamente eventos en el cliente.</span><span class="sxs-lookup"><span data-stu-id="413f3-108">Use this kind of contract when your service must query the client for more information or explicitly raise events on the client.</span></span> <span data-ttu-id="413f3-109">Para obtener más información sobre cómo crear una aplicación cliente para un contrato dúplex, consulte [Cómo: obtener acceso a los servicios con un contrato dúplex](how-to-access-services-with-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="413f3-109">For more information about creating a client application for a duplex contract, see [How to: Access Services with a Duplex Contract](how-to-access-services-with-a-duplex-contract.md).</span></span> <span data-ttu-id="413f3-110">Para obtener un ejemplo funcional, vea el ejemplo [dúplex](../samples/duplex.md) .</span><span class="sxs-lookup"><span data-stu-id="413f3-110">For a working sample, see the [Duplex](../samples/duplex.md) sample.</span></span>  
  
### <a name="to-create-a-duplex-contract"></a><span data-ttu-id="413f3-111">Creación de un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="413f3-111">To create a duplex contract</span></span>  
  
1. <span data-ttu-id="413f3-112">Cree la interfaz que crea el lado del servidor del contrato dúplex.</span><span class="sxs-lookup"><span data-stu-id="413f3-112">Create the interface that makes up the server side of the duplex contract.</span></span>  
  
2. <span data-ttu-id="413f3-113">Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz.</span><span class="sxs-lookup"><span data-stu-id="413f3-113">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3. <span data-ttu-id="413f3-114">Declare las firmas de los métodos en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="413f3-114">Declare the method signatures in the interface.</span></span>  
  
4. <span data-ttu-id="413f3-115">Aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada firma de método que debe formar parte del contrato público.</span><span class="sxs-lookup"><span data-stu-id="413f3-115">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
5. <span data-ttu-id="413f3-116">Cree la interfaz de devolución de llamada que define el conjunto de operaciones que el servicio puede invocar en el cliente.</span><span class="sxs-lookup"><span data-stu-id="413f3-116">Create the callback interface that defines the set of operations that the service can invoke on the client.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6. <span data-ttu-id="413f3-117">Declare las firmas de métodos en la interfaz de devolución de llamadas.</span><span class="sxs-lookup"><span data-stu-id="413f3-117">Declare the method signatures in the callback interface.</span></span>  
  
7. <span data-ttu-id="413f3-118">Aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada firma de método que debe formar parte del contrato público.</span><span class="sxs-lookup"><span data-stu-id="413f3-118">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
8. <span data-ttu-id="413f3-119">Vincule las dos interfaces en un contrato dúplex estableciendo la propiedad <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> de la interfaz principal en el tipo de la interfaz de devolución de llamadas.</span><span class="sxs-lookup"><span data-stu-id="413f3-119">Link the two interfaces into a duplex contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> property in the primary interface to the type of the callback interface.</span></span>  
  
### <a name="to-call-methods-on-the-client"></a><span data-ttu-id="413f3-120">Realización de llamadas a métodos en el cliente</span><span class="sxs-lookup"><span data-stu-id="413f3-120">To call methods on the client</span></span>  
  
1. <span data-ttu-id="413f3-121">En la implementación del servicio del contrato principal, declare una variable para la interfaz de devolución de llamadas.</span><span class="sxs-lookup"><span data-stu-id="413f3-121">In the service's implementation of the primary contract, declare a variable for the callback interface.</span></span>  
  
2. <span data-ttu-id="413f3-122">Establezca la variable en la referencia al objeto devuelta por el método <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> de la clase <xref:System.ServiceModel.OperationContext>.</span><span class="sxs-lookup"><span data-stu-id="413f3-122">Set the variable to the object reference returned by the <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> method of the <xref:System.ServiceModel.OperationContext> class.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3. <span data-ttu-id="413f3-123">Llame a los métodos definidos por la interfaz de devolución de llamadas.</span><span class="sxs-lookup"><span data-stu-id="413f3-123">Call the methods defined by the callback interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="413f3-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="413f3-124">Example</span></span>  
 <span data-ttu-id="413f3-125">El siguiente código de ejemplo muestra la comunicación dúplex.</span><span class="sxs-lookup"><span data-stu-id="413f3-125">The following code example demonstrates duplex communication.</span></span> <span data-ttu-id="413f3-126">El contrato del servicio contiene las operaciones del servicio para avanzar o retroceder.</span><span class="sxs-lookup"><span data-stu-id="413f3-126">The service’s contract contains service operations for moving forward and backward.</span></span> <span data-ttu-id="413f3-127">El contrato del cliente contiene una operación del servicio para informar sobre su posición.</span><span class="sxs-lookup"><span data-stu-id="413f3-127">The client’s contract contains a service operation for reporting its position.</span></span>  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
- <span data-ttu-id="413f3-128">La aplicación de los atributos <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute> permite la generación automática de definiciones de contrato de servicios en el Lenguaje de descripción de servicios Web (WSDL).</span><span class="sxs-lookup"><span data-stu-id="413f3-128">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes allows the automatic generation of service contract definitions in the Web Services Description Language (WSDL).</span></span>  
  
- <span data-ttu-id="413f3-129">Use la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para recuperar el documento WSDL y el código (opcional) y la configuración de un cliente.</span><span class="sxs-lookup"><span data-stu-id="413f3-129">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to retrieve the WSDL document and (optional) code and configuration for a client.</span></span>  
  
- <span data-ttu-id="413f3-130">Se deben proteger los extremos que exponen servicios dúplex.</span><span class="sxs-lookup"><span data-stu-id="413f3-130">Endpoints exposing duplex services must be secured.</span></span> <span data-ttu-id="413f3-131">Cuando un servicio recibe un mensaje dúplex, examina el elemento ReplyTo en ese mensaje entrante para determinar a dónde enviar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="413f3-131">When a service receives a duplex message, it looks at the ReplyTo in that incoming message to determine where to send the reply.</span></span> <span data-ttu-id="413f3-132">Si no se protege el canal, un cliente que no es de confianza podría enviar un mensaje malintencionado con un ReplyTo del equipo de destino, provocando una denegación de servicio del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="413f3-132">If the channel is not secured, then an untrusted client could send a malicious message with a target machine's ReplyTo, leading to a denial of service of the target machine.</span></span> <span data-ttu-id="413f3-133">Esto no es un problema con mensajes de solicitud-respuesta normales, porque el ReplyTo se pasa por alto y se envía la respuesta al canal en el que entró el mensaje original.</span><span class="sxs-lookup"><span data-stu-id="413f3-133">With regular request-reply messages, this is not an issue, because the ReplyTo is ignored and the response is sent on the channel the original message came in on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="413f3-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="413f3-134">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="413f3-135">Procedimiento para obtener acceso a los servicios con un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="413f3-135">How to: Access Services with a Duplex Contract</span></span>](how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="413f3-136">Dúplex</span><span class="sxs-lookup"><span data-stu-id="413f3-136">Duplex</span></span>](../samples/duplex.md)
- [<span data-ttu-id="413f3-137">Diseño e implementación de servicios</span><span class="sxs-lookup"><span data-stu-id="413f3-137">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)
- [<span data-ttu-id="413f3-138">Cómo definir un contrato de servicios</span><span class="sxs-lookup"><span data-stu-id="413f3-138">How to: Define a Service Contract</span></span>](../how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="413f3-139">Sesión</span><span class="sxs-lookup"><span data-stu-id="413f3-139">Session</span></span>](../samples/session.md)
