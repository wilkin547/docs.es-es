---
title: "C&#243;mo inspeccionar o modificar mensajes en el cliente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b8256335-f1c2-419f-b862-9f220ccad84c
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# C&#243;mo inspeccionar o modificar mensajes en el cliente
Puede inspeccionar o modificar los mensajes de entrada o de salida a través de un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementando <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName> e insertándolo en el tiempo de ejecución del cliente.  Para obtener más información, consulta [Extensión de clientes](../../../../docs/framework/wcf/extending/extending-clients.md).  La característica equivalente del servicio es <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName>.  Para ver un ejemplo de código completo, vea el ejemplo [Inspectores de mensaje](../../../../docs/framework/wcf/samples/message-inspectors.md).  
  
### Inspeccionar o modificar los mensajes  
  
1.  Implementar la interfaz <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName>.  
  
2.  Implemente <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName> o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName> según el ámbito en el que desee insertar el inspector de mensaje de cliente.  <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName>permite cambiar el comportamiento en el nivel de extremo.  <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName>permite cambiar el comportamiento en el nivel de contrato.  
  
3.  Inserte el comportamiento antes de llamar al método <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=fullName> o <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=fullName> en <xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName>.  Para obtener información detallada, vea [Configuración y extensión del tiempo de ejecución con comportamientos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## Ejemplo  
 Los siguientes ejemplos de código muestran, en orden:  
  
-   Una implementación de inspector de cliente.  
  
-   Un comportamiento del extremo que inserta el inspector.  
  
-   <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>\- clase derivada que permite agregar el comportamiento en un archivo de configuración.  
  
-   Un archivo de configuración que agrega el comportamiento del extremo que inserta el inspector de mensaje de cliente en el tiempo de ejecución del cliente.  
  
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
  
```vb  
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
  
## Vea también  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName>   
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName>   
 [Configuración y extensión del tiempo de ejecución con comportamientos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)