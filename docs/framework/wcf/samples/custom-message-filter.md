---
title: "Filtro de mensaje personalizado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98dd0af8-fce6-4255-ac32-42eb547eea67
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Filtro de mensaje personalizado
Este ejemplo muestra cómo reemplazar los filtros de mensajes que [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utiliza para enviar mensajes a los extremos.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Cuando el primer mensaje en un canal llega al servidor, el servidor debe determinar cual \(en caso necesario\) de los extremos asociados a ese URI debería recibir el mensaje.Los objetos <xref:System.ServiceModel.Dispatcher.MessageFilter> adjuntados a <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>controlan este proceso.  
  
 Cada extremo de un servicio tiene un <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>único.El <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> tiene ambos, un<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> y un <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>.La unión de estos dos filtros es el filtro de mensajes utilizado para ese extremo.  
  
 De forma predeterminada, <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> para un extremo coincide con cualquier mensaje que se dirige a una dirección que coincide con el extremo del servicio<xref:System.ServiceModel.EndpointAddress>.De forma predeterminada, el <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> para un extremo inspecciona la acción del mensaje entrante y coincide cualquier mensaje con una acción que corresponde a una de las acciones de las operaciones del contrato del extremo de servicio \(solo las acciones `IsInitiating`\=`true` están consideradas\).Como resultado, de forma predeterminada, el filtro para un extremo coincide solo si el encabezado del mensaje Para es <xref:System.ServiceModel.EndpointAddress> del extremo y la acción del mensaje coincide con una de las acciones de la operación del extremo.  
  
 Estos filtros se pueden cambiar utilizando un comportamiento.En el ejemplo, el servicio crea un<xref:System.ServiceModel.Description.IEndpointBehavior> que reemplaza <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> y <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> en <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:  
  
```  
class FilteringEndpointBehavior : IEndpointBehavior …  
```  
  
 Se definen dos filtros de la dirección:  
  
```  
// Matches any message whose To address contains the letter 'e'  
class MatchEAddressFilter : MessageFilter …  
// Matches any message whose To address does not contain the letter 'e'  
class MatchNoEAddressFilter : MessageFilter  
```  
  
 `FilteringEndpointBehavior` se vuelve configurable y permite dos variaciones diferentes.  
  
```  
public class FilteringEndpointBehaviorExtension : BehaviorExtensionElement  
  
```  
  
 La variación 1 solo coincide con direcciones que contienen una 'e' \(pero este tiene cualquier Acción\) mientras que la Variación 2 solo coincide con direcciones a las que les falta una 'e':  
  
```  
if (Variation == 1)  
    return new FilteringEndpointBehavior(  
        new MatchEAddressFilter(), new MatchAllMessageFilter());  
else  
    return new FilteringEndpointBehavior(  
        new MatchNoEAddressFilter(), new MatchAllMessageFilter());  
  
```  
  
 En el archivo de configuración, el servicio registra el nuevo comportamiento:  
  
```  
<extensions>  
    <behaviorExtensions>  
        <add name="filteringEndpointBehavior" type="Microsoft.ServiceModel.Samples.FilteringEndpointBehaviorExtension, service" />  
    </behaviorExtensions>  
</extensions>      
```  
  
 A continuación, el servicio crea las configuraciones `endpointBehavior` para cada variación:  
  
```  
<endpointBehaviors>  
    <behavior name="endpoint1">  
        <filteringEndpointBehavior variation="1" />  
    </behavior>  
    <behavior name="endpoint2">  
        <filteringEndpointBehavior variation="2" />  
    </behavior>  
</endpointBehaviors>  
  
```  
  
 Finalmente, el extremo del servicio hace referencia a uno de `behaviorConfigurations`:  
  
```  
<endpoint address=""  
        bindingConfiguration="ws"  
        listenUri=""   
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IHello"   
        behaviorConfiguration="endpoint2" />  
  
```  
  
 La implementación de la aplicación cliente es sencilla; crea dos canales al parámetro URI \(pasando ese valor como el segundo \(`via`\) del servicio a <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> y envía un mensaje único en cada canal, pero utiliza diferentes direcciones de extremos para cada uno.Como resultado, los mensajes salientes del cliente tienen diferentes designaciones Para y el servidor responde correspondientemente, como se muestra en el resultado del cliente:  
  
```  
Sending message to urn:e...  
Exception: The message with To 'urn:e' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher.  Check that the sender and receiver's EndpointAddresses agree.  
  
Sending message to urn:a...  
Hello  
```  
  
 Al intercambiar la variación en el archivo de configuración del servidor, el filtro se cambia y el cliente ve el comportamiento contrario \(el mensaje a `urn:e` tiene éxito, mientras que el mensaje a `urn:a` produce un error\).  
  
```  
<endpoint address=""  
          bindingConfiguration="ws"  
          listenUri=""   
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.IHello"   
          behaviorConfiguration="endpoint1" />  
  
```  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Extensibility\MessageFilter`  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Para compilar la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Para ejecutar el ejemplo en una configuración de equipos única, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración del equipo cruzado, siga las instrucciones en [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md) y cambie la línea siguiente en Client.cs.  
  
    ```  
    Uri serviceVia = new Uri("http://localhost/ServiceModelSamples/service.svc");  
    ```  
  
     Reemplace el localhost con el nombre de servidor.  
  
    ```  
    Uri serviceVia = new Uri("http://servermachinename/ServiceModelSamples/service.svc");  
    ```  
  
## Vea también