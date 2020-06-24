---
title: Procedimiento para inspeccionar o modificar mensajes en el cliente
description: Obtenga información sobre cómo inspeccionar o modificar los mensajes entrantes o salientes a través de un cliente o servicio WCF implementando la interfaz adecuada.
ms.date: 03/30/2017
ms.assetid: b8256335-f1c2-419f-b862-9f220ccad84c
ms.openlocfilehash: 6f6a3d20d7f3a9fb79de5cd3e29096e270d0f188
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247512"
---
# <a name="how-to-inspect-or-modify-messages-on-the-client"></a>Procedimiento para inspeccionar o modificar mensajes en el cliente
Puede inspeccionar o modificar los mensajes entrantes o salientes a través de un cliente WCF implementando <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> e insertando en el tiempo de ejecución del cliente. Para obtener más información, consulte [Extending clients](extending-clients.md). La característica equivalente del servicio es <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>. Para obtener un ejemplo de código completo, vea el ejemplo de [inspectores de mensajes](../samples/message-inspectors.md) .  
  
### <a name="to-inspect-or-modify-messages"></a>Inspeccionar o modificar los mensajes  
  
1. Implemente la interfaz <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.  
  
2. Implemente <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> según el ámbito en el que desee insertar el inspector de mensaje de cliente. <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>permite cambiar el comportamiento en el nivel de extremo. <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>permite cambiar el comportamiento en el nivel de contrato.  
  
3. Inserte el comportamiento antes de llamar al método <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Para obtener más información, consulte [configuración y extensión del tiempo de ejecución con comportamientos](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Ejemplo  
 Los siguientes ejemplos de código muestran, en orden:  
  
- Una implementación de inspector de cliente.  
  
- Un comportamiento del punto de conexión que inserta el inspector.  
  
- <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>- clase derivada que permite agregar el comportamiento en un archivo de configuración.  
  
- Un archivo de configuración que agrega el comportamiento del extremo que inserta el inspector de mensaje de cliente en el tiempo de ejecución del cliente.  
  
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
                      behaviorConfiguration="clientInspectorsAdded"
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
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [Configuración y extensión del tiempo de ejecución con comportamientos](configuring-and-extending-the-runtime-with-behaviors.md)
