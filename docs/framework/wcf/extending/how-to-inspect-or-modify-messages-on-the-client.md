---
title: "Cómo inspeccionar o modificar mensajes en el cliente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8256335-f1c2-419f-b862-9f220ccad84c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 06f4feaa5b0b44a26e3d31b65dc465b67544482f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-inspect-or-modify-messages-on-the-client"></a><span data-ttu-id="0110c-102">Cómo inspeccionar o modificar mensajes en el cliente</span><span class="sxs-lookup"><span data-stu-id="0110c-102">How to: Inspect or Modify Messages on the Client</span></span>
<span data-ttu-id="0110c-103">Puede inspeccionar o modificar los mensajes de entrada o de salida a través de un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementando <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> e insertándolo en el tiempo de ejecución del cliente.</span><span class="sxs-lookup"><span data-stu-id="0110c-103">You can inspect or modify the incoming or outgoing messages across a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client by implementing a <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> and inserting it into the client runtime.</span></span> <span data-ttu-id="0110c-104">Para obtener más información, consulte [clientes extender](../../../../docs/framework/wcf/extending/extending-clients.md).</span><span class="sxs-lookup"><span data-stu-id="0110c-104">For more information, see [Extending Clients](../../../../docs/framework/wcf/extending/extending-clients.md).</span></span> <span data-ttu-id="0110c-105">La característica equivalente del servicio es <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0110c-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0110c-106">Para obtener un ejemplo de código completo, vea el [inspectores de mensaje](../../../../docs/framework/wcf/samples/message-inspectors.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0110c-106">For a complete code example see the [Message Inspectors](../../../../docs/framework/wcf/samples/message-inspectors.md) sample.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="0110c-107">Inspeccionar o modificar los mensajes</span><span class="sxs-lookup"><span data-stu-id="0110c-107">To inspect or modify messages</span></span>  
  
1.  <span data-ttu-id="0110c-108">Implementar la interfaz <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0110c-108">Implement the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2.  <span data-ttu-id="0110c-109">Implemente <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> según el ámbito en el que desee insertar el inspector de mensaje de cliente.</span><span class="sxs-lookup"><span data-stu-id="0110c-109">Implement a <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> depending upon the scope at which you want to insert the client message inspector.</span></span> <span data-ttu-id="0110c-110"><xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>permite cambiar el comportamiento en el nivel del extremo.</span><span class="sxs-lookup"><span data-stu-id="0110c-110"><xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> allows you to change behavior at the endpoint level.</span></span> <span data-ttu-id="0110c-111"><xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>permite cambiar el comportamiento en el nivel del contrato.</span><span class="sxs-lookup"><span data-stu-id="0110c-111"><xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> allows you to change behavior at the contract level.</span></span>  
  
3.  <span data-ttu-id="0110c-112">Inserte el comportamiento antes de llamar al método <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0110c-112">Insert the behavior prior to calling the <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0110c-113">Para obtener más información, consulte [configuración y al ampliar el tiempo de ejecución con comportamientos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="0110c-113">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0110c-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0110c-114">Example</span></span>  
 <span data-ttu-id="0110c-115">Los siguientes ejemplos de código muestran, en orden:</span><span class="sxs-lookup"><span data-stu-id="0110c-115">The following code examples show, in order:</span></span>  
  
-   <span data-ttu-id="0110c-116">Una implementación de inspector de cliente.</span><span class="sxs-lookup"><span data-stu-id="0110c-116">A client inspector implementation.</span></span>  
  
-   <span data-ttu-id="0110c-117">Un comportamiento del extremo que inserta el inspector.</span><span class="sxs-lookup"><span data-stu-id="0110c-117">An endpoint behavior that inserts the inspector.</span></span>  
  
-   <span data-ttu-id="0110c-118"><xref:System.ServiceModel.Configuration.BehaviorExtensionElement>- clase derivada que permite agregar el comportamiento en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="0110c-118">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>- derived class that allows you to add the behavior in a configuration file.</span></span>  
  
-   <span data-ttu-id="0110c-119">Un archivo de configuración que agrega el comportamiento del punto de conexión que inserta el inspector de mensaje de cliente en el tiempo de ejecución del cliente.</span><span class="sxs-lookup"><span data-stu-id="0110c-119">A configuration file that adds the endpoint behavior which inserts the client message inspector into the client runtime.</span></span>  
  
```csharp  
// Client message inspector  
public class SimpleMessageInspector : IClientMessageInspector  
{  
    public void AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
    {  
        // Implement this method to inspect/modify messages after a message  
        // is received but prior to passing it back to the client   
        Console.WriteLine("AfterReceiveReply called");  
    }  
  
    public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, IClientChannel channel)  
    {  
        // Implement this method to inspect/modify messages before they   
        // are sent to the service  
        Console.WriteLine("BeforeSendRequest called");  
        return null;  
    }  
}  
```  
  
```csharp  
// Endpoint behavior  
public class SimpleEndpointBehavior : IEndpointBehavior  
{  
    public void AddBindingParameters(ServiceEndpoint endpoint, System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
    {  
         // No implementation necessary  
    }  
  
    public void ApplyClientBehavior(ServiceEndpoint endpoint, ClientRuntime clientRuntime)  
    {  
        clientRuntime.MessageInspectors.Add(new SimpleMessageInspector());  
    }  
  
    public void ApplyDispatchBehavior(ServiceEndpoint endpoint, EndpointDispatcher endpointDispatcher)  
    {  
         // No implementation necessary  
    }  
  
    public void Validate(ServiceEndpoint endpoint)  
    {  
         // No implementation necessary  
    }  
}  
```  
  
```csharp  
// Configuration element   
public class SimpleBehaviorExtensionElement : BehaviorExtensionElement  
{  
    public override Type BehaviorType  
    {  
        get { return typeof(SimpleEndpointBehavior); }  
    }  
  
    protected override object CreateBehavior()  
    {  
         // Create the  endpoint behavior that will insert the message  
         // inspector into the client runtime  
        return new SimpleEndpointBehavior();  
    }  
}  
```  
  
```xml
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <system.serviceModel>  
        <client>  
            <endpoint address="http://localhost:8080/SimpleService/"   
                      binding="wsHttpBinding"  
                      contract="ServiceReference1.IService1"  
                      name="WSHttpBinding_IService1"/>  
        </client>  
  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="clientInspectorsAdded">  
            <simpleBehaviorExtension />  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <extensions>  
        <behaviorExtensions>  
          <add  
            name="simpleBehaviorExtension"  
            type="SimpleServiceLib.SimpleBehaviorExtensionElement, Host, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0110c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0110c-120">See Also</span></span>  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>  
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>  
 [<span data-ttu-id="0110c-121">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="0110c-121">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
