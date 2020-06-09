---
title: Filtro de mensaje personalizado
ms.date: 03/30/2017
ms.assetid: 98dd0af8-fce6-4255-ac32-42eb547eea67
ms.openlocfilehash: 0e4da0f2283fd537afe3cacdddfb36c327cfd3b4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600049"
---
# <a name="custom-message-filter"></a>Filtro de mensaje personalizado
Este ejemplo muestra cómo reemplazar los filtros de mensajes que utiliza Windows Communication Foundation (WCF) para enviar mensajes a los extremos.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Cuando el primer mensaje en un canal llega al servidor, el servidor debe determinar cual (en caso necesario) de los puntos de conexión asociados a ese URI debería recibir el mensaje. Los objetos <xref:System.ServiceModel.Dispatcher.MessageFilter> adjuntados a <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>controlan este proceso.  
  
 Cada extremo de un servicio tiene un <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>único. El <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> tiene ambos, un<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> y un <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>. La unión de estos dos filtros es el filtro de mensajes utilizado para ese punto de conexión.  
  
 De forma predeterminada, <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> para un punto de conexión coincide con cualquier mensaje que se dirige a una dirección que coincide con el punto de conexión del servicio<xref:System.ServiceModel.EndpointAddress>. De forma predeterminada, <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> para un punto de conexión inspecciona la acción del mensaje entrante y coincide con cualquier mensaje con una acción que corresponde a una de las acciones de las operaciones del contrato del punto de conexión de servicio (solo se tienen en `IsInitiating` = `true` cuenta las acciones). Como resultado, de forma predeterminada, el filtro para un punto de conexión coincide solo si el encabezado del mensaje Para es <xref:System.ServiceModel.EndpointAddress> del punto de conexión y la acción del mensaje coincide con una de las acciones de la operación del punto de conexión.  
  
 Estos filtros se pueden cambiar utilizando un comportamiento. En el ejemplo, el servicio crea un<xref:System.ServiceModel.Description.IEndpointBehavior> que reemplaza <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> y <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> en <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:  
  
```csharp
class FilteringEndpointBehavior : IEndpointBehavior
{
    //...
}
```  
  
 Se definen dos filtros de la dirección:  
  
```csharp
// Matches any message whose To address contains the letter 'e'  
class MatchEAddressFilter : MessageFilter { }
// Matches any message whose To address does not contain the letter 'e'  
class MatchNoEAddressFilter : MessageFilter { }  
```  
  
 `FilteringEndpointBehavior` se vuelve configurable y permite dos variaciones diferentes.  
  
```csharp
public class FilteringEndpointBehaviorExtension : BehaviorExtensionElement { }
```  
  
 La variación 1 solo coincide con direcciones que contienen una 'e' (pero este tiene cualquier Acción) mientras que la Variación 2 solo coincide con direcciones a las que les falta una 'e':  
  
```csharp
if (Variation == 1)  
    return new FilteringEndpointBehavior(  
        new MatchEAddressFilter(), new MatchAllMessageFilter());  
else  
    return new FilteringEndpointBehavior(  
        new MatchNoEAddressFilter(), new MatchAllMessageFilter());  
```  
  
 En el archivo de configuración, el servicio registra el nuevo comportamiento:  
  
```xml  
<extensions>  
    <behaviorExtensions>  
        <add name="filteringEndpointBehavior" type="Microsoft.ServiceModel.Samples.FilteringEndpointBehaviorExtension, service" />  
    </behaviorExtensions>  
</extensions>
```  
  
 A continuación, el servicio crea las configuraciones `endpointBehavior` para cada variación:  
  
```xml  
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
  
```xml  
<endpoint address=""  
        bindingConfiguration="ws"  
        listenUri=""
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IHello"
        behaviorConfiguration="endpoint2" />  
```  
  
 La implementación de la aplicación cliente es sencilla; crea dos canales al parámetro URI (pasando ese valor como el segundo (`via`) del servicio a <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> y envía un mensaje único en cada canal, pero utiliza diferentes direcciones de puntos de conexión para cada uno. Como resultado, los mensajes salientes del cliente tienen diferentes designaciones Para y el servidor responde correspondientemente, como se muestra en el resultado del cliente:  
  
```console  
Sending message to urn:e...  
Exception: The message with To 'urn:e' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher.  Check that the sender and receiver's EndpointAddresses agree.  
  
Sending message to urn:a...  
Hello  
```  
  
 Al intercambiar la variación en el archivo de configuración del servidor, el filtro se cambia y el cliente ve el comportamiento contrario (el mensaje a `urn:e` tiene éxito, mientras que el mensaje a `urn:a` produce un error).  
  
```xml  
<endpoint address=""  
          bindingConfiguration="ws"  
          listenUri=""
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.IHello"
          behaviorConfiguration="endpoint1" />  
```  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageFilter`  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).  
  
2. Para ejecutar el ejemplo en una configuración de un solo equipo, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos cruzados, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md) y cambie la línea siguiente en Client.cs.  
  
    ```csharp
    Uri serviceVia = new Uri("http://localhost/ServiceModelSamples/service.svc");  
    ```  
  
     Reemplace el localhost con el nombre de servidor.  
  
    ```csharp
    Uri serviceVia = new Uri("http://servermachinename/ServiceModelSamples/service.svc");  
    ```  
