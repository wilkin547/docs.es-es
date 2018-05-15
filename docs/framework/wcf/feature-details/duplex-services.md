---
title: Servicios dúplex
ms.date: 05/09/2018
dev_langs:
- csharp
- vb
ms.assetid: 396b875a-d203-4ebe-a3a1-6a330d962e95
ms.openlocfilehash: da92b8f2d1223f582677a93a8ff6fd697512d297
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
---
# <a name="duplex-services"></a><span data-ttu-id="3aafe-102">Servicios dúplex</span><span class="sxs-lookup"><span data-stu-id="3aafe-102">Duplex Services</span></span>
<span data-ttu-id="3aafe-103">Un contrato de servicios dúplex es un patrón de intercambio de mensajes en el que ambos extremos pueden enviar mensajes al otro de manera independiente.</span><span class="sxs-lookup"><span data-stu-id="3aafe-103">A duplex service contract is a message exchange pattern in which both endpoints can send messages to the other independently.</span></span> <span data-ttu-id="3aafe-104">Un servicio dúplex, por tanto, puede enviar mensajes de vuelta al extremo del cliente, proporcionando un comportamiento parecido a los eventos.</span><span class="sxs-lookup"><span data-stu-id="3aafe-104">A duplex service, therefore, can send messages back to the client endpoint, providing event-like behavior.</span></span> <span data-ttu-id="3aafe-105">La comunicación dúplex se produce cuando un cliente se conecta a un servicio y proporciona al servicio un canal en el que el servicio puede devolver los mensajes al cliente.</span><span class="sxs-lookup"><span data-stu-id="3aafe-105">Duplex communication occurs when a client connects to a service and provides the service with a channel on which the service can send messages back to the client.</span></span> <span data-ttu-id="3aafe-106">Tenga en cuenta que el comportamiento como evento de los servicios dúplex solo funciona dentro de una sesión.</span><span class="sxs-lookup"><span data-stu-id="3aafe-106">Note that the event-like behavior of duplex services only works within a session.</span></span>  
  
 <span data-ttu-id="3aafe-107">Para crear un contrato dúplex ha de crear un par de interfaces.</span><span class="sxs-lookup"><span data-stu-id="3aafe-107">To create a duplex contract you create a pair of interfaces.</span></span> <span data-ttu-id="3aafe-108">La primera es la interfaz del contrato de servicio, que describe las operaciones que un cliente puede invocar.</span><span class="sxs-lookup"><span data-stu-id="3aafe-108">The first is the service contract interface that describes the operations that a client can invoke.</span></span> <span data-ttu-id="3aafe-109">Ese contrato de servicio debe especificar un *contrato de devolución de llamada* en el <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="3aafe-109">That service contract must specify a *callback contract* in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="3aafe-110">El contrato de devolución de llamadas es la interfaz que define las operaciones a las que el servicio puede llamar en el punto de conexión del cliente.</span><span class="sxs-lookup"><span data-stu-id="3aafe-110">The callback contract is the interface that defines the operations that the service can call on the client endpoint.</span></span> <span data-ttu-id="3aafe-111">Un contrato dúplex no requiere una sesión, aunque los enlaces dúplex proporcionados por el sistema las utilizan.</span><span class="sxs-lookup"><span data-stu-id="3aafe-111">A duplex contract does not require a session, although the system-provided duplex bindings make use of them.</span></span>  
  
 <span data-ttu-id="3aafe-112">A continuación, se muestra un ejemplo de un contrato dúplex.</span><span class="sxs-lookup"><span data-stu-id="3aafe-112">The following is an example of a duplex contract.</span></span>  
  
 [!code-csharp[c_DuplexServices#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#0)]
 [!code-vb[c_DuplexServices#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#0)]  
  
 <span data-ttu-id="3aafe-113">La clase `CalculatorService` implementa la interfaz principal `ICalculatorDuplex`.</span><span class="sxs-lookup"><span data-stu-id="3aafe-113">The `CalculatorService` class implements the primary `ICalculatorDuplex` interface.</span></span> <span data-ttu-id="3aafe-114">El servicio utiliza el modo de instancia <xref:System.ServiceModel.InstanceContextMode.PerSession> para mantener el resultado para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="3aafe-114">The service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the result for each session.</span></span> <span data-ttu-id="3aafe-115">Una propiedad privada denominada `Callback` tiene acceso al canal de devolución de llamadas hasta el cliente.</span><span class="sxs-lookup"><span data-stu-id="3aafe-115">A private property named `Callback` accesses the callback channel to the client.</span></span> <span data-ttu-id="3aafe-116">El servicio utiliza la devolución de llamadas para devolver los mensajes al cliente a través de la interfaz de devolución de llamadas, como se muestra en el siguiente código de muestra.</span><span class="sxs-lookup"><span data-stu-id="3aafe-116">The service uses the callback for sending messages back to the client through the callback interface, as shown in the following sample code.</span></span>  
  
 [!code-csharp[c_DuplexServices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#1)]
 [!code-vb[c_DuplexServices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#1)]  
  
 <span data-ttu-id="3aafe-117">El cliente debe proporcionar una clase que implemente la interfaz de devolución de llamadas del contrato dúplex para recibir los mensajes del servicio.</span><span class="sxs-lookup"><span data-stu-id="3aafe-117">The client must provide a class that implements the callback interface of the duplex contract, for receiving messages from the service.</span></span> <span data-ttu-id="3aafe-118">En el siguiente ejemplo de código se muestra una clase `CallbackHandler` que implementa la interfaz `ICalculatorDuplexCallback`.</span><span class="sxs-lookup"><span data-stu-id="3aafe-118">The following sample code shows a `CallbackHandler` class that implements the `ICalculatorDuplexCallback` interface.</span></span>  
  
 [!code-csharp[c_DuplexServices#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#2)]
 [!code-vb[c_DuplexServices#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#2)]  
  
 <span data-ttu-id="3aafe-119">El cliente WCF que se genera para un contrato dúplex requiere una <xref:System.ServiceModel.InstanceContext> clase proporcionarse en la construcción.</span><span class="sxs-lookup"><span data-stu-id="3aafe-119">The WCF client that is generated for a duplex contract requires a <xref:System.ServiceModel.InstanceContext> class to be provided upon construction.</span></span> <span data-ttu-id="3aafe-120">Esta clase <xref:System.ServiceModel.InstanceContext> se utiliza como sitio para un objeto que implementa la interfaz de devolución de llamadas y administra mensajes que se devuelven desde el servicio.</span><span class="sxs-lookup"><span data-stu-id="3aafe-120">This <xref:System.ServiceModel.InstanceContext> class is used as the site for an object that implements the callback interface and handles messages that are sent back from the service.</span></span> <span data-ttu-id="3aafe-121">Se construye una clase <xref:System.ServiceModel.InstanceContext> con una instancia de la clase `CallbackHandler`.</span><span class="sxs-lookup"><span data-stu-id="3aafe-121">An <xref:System.ServiceModel.InstanceContext> class is constructed with an instance of the `CallbackHandler` class.</span></span> <span data-ttu-id="3aafe-122">Este objeto administra mensajes enviados desde el servicio al cliente en la interfaz de devolución de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3aafe-122">This object handles messages sent from the service to the client on the callback interface.</span></span>  
  
 [!code-csharp[c_DuplexServices#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#3)]
 [!code-vb[c_DuplexServices#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#3)]  
  
 <span data-ttu-id="3aafe-123">La configuración del servicio debe realizarse para proporcionar un enlace que admita comunicación de la sesión y dúplex.</span><span class="sxs-lookup"><span data-stu-id="3aafe-123">The configuration for the service must be set up to provide a binding that supports both session communication and duplex communication.</span></span> <span data-ttu-id="3aafe-124">El elemento `wsDualHttpBinding` admite la comunicación de la sesión y permite la comunicación dúplex proporcionando conexiones HTTP duales, una para cada dirección.</span><span class="sxs-lookup"><span data-stu-id="3aafe-124">The `wsDualHttpBinding` element supports session communication and allows duplex communication by providing dual HTTP connections, one for each direction.</span></span>  
  
 <span data-ttu-id="3aafe-125">En el cliente, debe configurar una dirección que el servidor pueda utilizar para conectarse al cliente, como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3aafe-125">On the client, you must configure an address that the server can use to connect to the client, as shown in the following sample configuration.</span></span>  
  
  
  
> [!NOTE]
>  <span data-ttu-id="3aafe-126">Además, los clientes que no sean dúplex y que no se autentiquen mediante una conversación segura, normalmente, producen una <xref:System.ServiceModel.Security.MessageSecurityException>.</span><span class="sxs-lookup"><span data-stu-id="3aafe-126">Non-duplex clients that fail to authenticate using a secure conversation typically throw a <xref:System.ServiceModel.Security.MessageSecurityException>.</span></span> <span data-ttu-id="3aafe-127">Sin embargo, si un cliente dúplex que utiliza una conversación segura no se autentica, el cliente recibe una <xref:System.TimeoutException>.</span><span class="sxs-lookup"><span data-stu-id="3aafe-127">However, if a duplex client that uses a secure conversation fails to authenticate, the client receives a <xref:System.TimeoutException> instead.</span></span>  
  
 <span data-ttu-id="3aafe-128">Si crea un cliente/servicio mediante el elemento `WSHttpBinding` y no incluye el extremo de devolución de llamada de cliente, recibirá el siguiente error.</span><span class="sxs-lookup"><span data-stu-id="3aafe-128">If you create a client/service using the `WSHttpBinding` element and you do not include the client callback endpoint, you will receive the following error.</span></span>  
  
```  
HTTP could not register URL  
htp://+:80/Temporary_Listen_Addresses/<guid> because TCP port 80 is being used by another application.  
```  
  
 <span data-ttu-id="3aafe-129">El código de ejemplo siguiente muestra cómo especificar al cliente de dirección de punto de conexión mediante programación.</span><span class="sxs-lookup"><span data-stu-id="3aafe-129">The following sample code shows how to specify the client endpoint address programmatically.</span></span>
  
```csharp  
WSDualHttpBinding binding = new WSDualHttpBinding();  
EndpointAddress endptadr = new EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server");  
binding.ClientBaseAddress = new Uri("http://localhost:8000/DuplexTestUsingCode/Client/");  
```  
```vb
Dim binding As New WSDualHttpBinding()
Dim endptadr As New EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server")
binding.ClientBaseAddress = New Uri("http://localhost:8000/DuplexTestUsingCode/Client/")  
```

 <span data-ttu-id="3aafe-130">El siguiente ejemplo de código muestra cómo especificar la dirección de punto de conexión de cliente mediante configuración.</span><span class="sxs-lookup"><span data-stu-id="3aafe-130">The following sample code shows how to specify the client endpoint address in configuration.</span></span>  
  
```xml  
<client>  
    <endpoint name ="ServerEndpoint"   
          address="http://localhost:12000/DuplexTestUsingConfig/Server"  
          bindingConfiguration="WSDualHttpBinding_IDuplexTest"   
            binding="wsDualHttpBinding"  
           contract="IDuplexTest" />  
</client>  
<bindings>  
    <wsDualHttpBinding>  
        <binding name="WSDualHttpBinding_IDuplexTest"    
          clientBaseAddress="http://localhost:8000/myClient/" >  
            <security mode="None"/>  
         </binding>  
    </wsDualHttpBinding>  
</bindings>  
```  
  
> [!WARNING]
>  <span data-ttu-id="3aafe-131">El modelo dúplex no detecta automáticamente cuando un servicio o cliente cierra su canal.</span><span class="sxs-lookup"><span data-stu-id="3aafe-131">The duplex model does not automatically detect when a service or client closes its channel.</span></span> <span data-ttu-id="3aafe-132">Por tanto, si un cliente finaliza inesperadamente, de forma predeterminada no se notificará al servicio.</span><span class="sxs-lookup"><span data-stu-id="3aafe-132">So if a client unexpectedly terminates, by default the service will not be notified, or if a client unexpectedly terminates, the service will not be notified.</span></span> <span data-ttu-id="3aafe-133">Los clientes y los servicios pueden implementar su propio protocolo para notificarse si así lo deciden.</span><span class="sxs-lookup"><span data-stu-id="3aafe-133">Clients and services can implement their own protocol to notify each other if they so choose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aafe-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="3aafe-134">See Also</span></span>  
 [<span data-ttu-id="3aafe-135">Dúplex</span><span class="sxs-lookup"><span data-stu-id="3aafe-135">Duplex</span></span>](../../../../docs/framework/wcf/samples/duplex.md)  
 [<span data-ttu-id="3aafe-136">Especificación del comportamiento de tiempo de ejecución del cliente</span><span class="sxs-lookup"><span data-stu-id="3aafe-136">Specifying Client Run-Time Behavior</span></span>](../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [<span data-ttu-id="3aafe-137">Creación de un generador de canales y utilizarlo para crear y gestionar canales</span><span class="sxs-lookup"><span data-stu-id="3aafe-137">How to: Create a Channel Factory and Use it to Create and Manage Channels</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels.md)
