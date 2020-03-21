---
title: Filtro de mensaje personalizado
ms.date: 03/30/2017
ms.assetid: 98dd0af8-fce6-4255-ac32-42eb547eea67
ms.openlocfilehash: 896407a218073eba53676baa4bcbd125593c80ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183882"
---
# <a name="custom-message-filter"></a><span data-ttu-id="8aedd-102">Filtro de mensaje personalizado</span><span class="sxs-lookup"><span data-stu-id="8aedd-102">Custom Message Filter</span></span>
<span data-ttu-id="8aedd-103">En este ejemplo se muestra cómo reemplazar los filtros de mensajes que Windows Communication Foundation (WCF) usa para enviar mensajes a los extremos.</span><span class="sxs-lookup"><span data-stu-id="8aedd-103">This sample demonstrates how to replace the message filters that Windows Communication Foundation (WCF) uses to dispatch messages to endpoints.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8aedd-104">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="8aedd-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8aedd-105">Cuando el primer mensaje en un canal llega al servidor, el servidor debe determinar cual (en caso necesario) de los puntos de conexión asociados a ese URI debería recibir el mensaje.</span><span class="sxs-lookup"><span data-stu-id="8aedd-105">When the first message on a channel arrives at the server, the server must determine which (if any) of the endpoints associated with that URI should receive the message.</span></span> <span data-ttu-id="8aedd-106">Los objetos <xref:System.ServiceModel.Dispatcher.MessageFilter> adjuntados a <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>controlan este proceso.</span><span class="sxs-lookup"><span data-stu-id="8aedd-106">This process is controlled by the <xref:System.ServiceModel.Dispatcher.MessageFilter> objects attached to the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span></span>  
  
 <span data-ttu-id="8aedd-107">Cada extremo de un servicio tiene un <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>único.</span><span class="sxs-lookup"><span data-stu-id="8aedd-107">Each endpoint of a service has a single <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span></span> <span data-ttu-id="8aedd-108">El <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> tiene ambos, un<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> y un <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>.</span><span class="sxs-lookup"><span data-stu-id="8aedd-108">The <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> has both an <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> and a <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>.</span></span> <span data-ttu-id="8aedd-109">La unión de estos dos filtros es el filtro de mensajes utilizado para ese punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8aedd-109">The union of these two filters is the message filter used for that endpoint.</span></span>  
  
 <span data-ttu-id="8aedd-110">De forma predeterminada, <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> para un punto de conexión coincide con cualquier mensaje que se dirige a una dirección que coincide con el punto de conexión del servicio<xref:System.ServiceModel.EndpointAddress>.</span><span class="sxs-lookup"><span data-stu-id="8aedd-110">By default, the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> for an endpoint matches any message that is addressed to an address that matches the service endpoint's <xref:System.ServiceModel.EndpointAddress>.</span></span> <span data-ttu-id="8aedd-111">De forma <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> predeterminada, el punto de conexión de un punto de conexión inspecciona la acción del mensaje entrante y `IsInitiating` = `true` hace coincidir cualquier mensaje con una acción que corresponde a una de las acciones de las operaciones del contrato de punto de conexión de servicio (solo se tienen en cuenta las acciones).</span><span class="sxs-lookup"><span data-stu-id="8aedd-111">By default, the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> for an endpoint inspects the action of the incoming message and matches any message with an action that corresponds to one of the actions of the service endpoint contract's operations (only `IsInitiating`=`true` actions are considered).</span></span> <span data-ttu-id="8aedd-112">Como resultado, de forma predeterminada, el filtro para un punto de conexión coincide solo si el encabezado del mensaje Para es <xref:System.ServiceModel.EndpointAddress> del punto de conexión y la acción del mensaje coincide con una de las acciones de la operación del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8aedd-112">As a result, by default, the filter for an endpoint only matches if both the message's To header is the <xref:System.ServiceModel.EndpointAddress> of the endpoint and the message's action matches one of the endpoint operation's actions.</span></span>  
  
 <span data-ttu-id="8aedd-113">Estos filtros se pueden cambiar utilizando un comportamiento.</span><span class="sxs-lookup"><span data-stu-id="8aedd-113">These filters can be changed using a behavior.</span></span> <span data-ttu-id="8aedd-114">En el ejemplo, el servicio crea un<xref:System.ServiceModel.Description.IEndpointBehavior> que reemplaza <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> y <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> en <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:</span><span class="sxs-lookup"><span data-stu-id="8aedd-114">In the sample, the service creates an <xref:System.ServiceModel.Description.IEndpointBehavior> that replaces the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> and <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> on the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:</span></span>  
  
```csharp
class FilteringEndpointBehavior : IEndpointBehavior
{
    //...
}
```  
  
 <span data-ttu-id="8aedd-115">Se definen dos filtros de la dirección:</span><span class="sxs-lookup"><span data-stu-id="8aedd-115">Two address filters are defined:</span></span>  
  
```csharp
// Matches any message whose To address contains the letter 'e'  
class MatchEAddressFilter : MessageFilter { }
// Matches any message whose To address does not contain the letter 'e'  
class MatchNoEAddressFilter : MessageFilter { }  
```  
  
 <span data-ttu-id="8aedd-116">`FilteringEndpointBehavior` se vuelve configurable y permite dos variaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="8aedd-116">The `FilteringEndpointBehavior` is made configurable and allows for two different variations.</span></span>  
  
```csharp
public class FilteringEndpointBehaviorExtension : BehaviorExtensionElement { }
```  
  
 <span data-ttu-id="8aedd-117">La variación 1 solo coincide con direcciones que contienen una 'e' (pero este tiene cualquier Acción) mientras que la Variación 2 solo coincide con direcciones a las que les falta una 'e':</span><span class="sxs-lookup"><span data-stu-id="8aedd-117">Variation 1 matches only addresses that contain an 'e' (but that have any Action) whereas Variation 2 matches only addresses that lack an 'e':</span></span>  
  
```csharp
if (Variation == 1)  
    return new FilteringEndpointBehavior(  
        new MatchEAddressFilter(), new MatchAllMessageFilter());  
else  
    return new FilteringEndpointBehavior(  
        new MatchNoEAddressFilter(), new MatchAllMessageFilter());  
```  
  
 <span data-ttu-id="8aedd-118">En el archivo de configuración, el servicio registra el nuevo comportamiento:</span><span class="sxs-lookup"><span data-stu-id="8aedd-118">In the configuration file, the service registers the new behavior:</span></span>  
  
```xml  
<extensions>  
    <behaviorExtensions>  
        <add name="filteringEndpointBehavior" type="Microsoft.ServiceModel.Samples.FilteringEndpointBehaviorExtension, service" />  
    </behaviorExtensions>  
</extensions>
```  
  
 <span data-ttu-id="8aedd-119">A continuación, el servicio crea las configuraciones `endpointBehavior` para cada variación:</span><span class="sxs-lookup"><span data-stu-id="8aedd-119">Then the service creates `endpointBehavior` configurations for each variation:</span></span>  
  
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
  
 <span data-ttu-id="8aedd-120">Finalmente, el extremo del servicio hace referencia a uno de `behaviorConfigurations`:</span><span class="sxs-lookup"><span data-stu-id="8aedd-120">Finally, the service's endpoint references one of the `behaviorConfigurations`:</span></span>  
  
```xml  
<endpoint address=""  
        bindingConfiguration="ws"  
        listenUri=""
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IHello"
        behaviorConfiguration="endpoint2" />  
```  
  
 <span data-ttu-id="8aedd-121">La implementación de la aplicación cliente es sencilla; crea dos canales al parámetro URI (pasando ese valor como el segundo (`via`) del servicio a <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> y envía un mensaje único en cada canal, pero utiliza diferentes direcciones de puntos de conexión para cada uno.</span><span class="sxs-lookup"><span data-stu-id="8aedd-121">The implementation of the client application is straightforward; it creates two channels to the service's URI (by passing in that value as the second (`via`) parameter to <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> and sends a single message on each channel, but it uses different endpoint addresses for each.</span></span> <span data-ttu-id="8aedd-122">Como resultado, los mensajes salientes del cliente tienen diferentes designaciones Para y el servidor responde correspondientemente, como se muestra en el resultado del cliente:</span><span class="sxs-lookup"><span data-stu-id="8aedd-122">As a result, the outbound messages from the client have different To designations, and the server responds accordingly, as demonstrated by the client's output:</span></span>  
  
```console  
Sending message to urn:e...  
Exception: The message with To 'urn:e' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher.  Check that the sender and receiver's EndpointAddresses agree.  
  
Sending message to urn:a...  
Hello  
```  
  
 <span data-ttu-id="8aedd-123">Al intercambiar la variación en el archivo de configuración del servidor, el filtro se cambia y el cliente ve el comportamiento contrario (el mensaje a `urn:e` tiene éxito, mientras que el mensaje a `urn:a` produce un error).</span><span class="sxs-lookup"><span data-stu-id="8aedd-123">Switching the variation in the server's configuration file causes the filter to be swapped and the client sees the opposite behavior (the message to `urn:e` succeeds, whereas the message to `urn:a` fails).</span></span>  
  
```xml  
<endpoint address=""  
          bindingConfiguration="ws"  
          listenUri=""
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.IHello"
          behaviorConfiguration="endpoint1" />  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="8aedd-124">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8aedd-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8aedd-125">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8aedd-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="8aedd-126">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8aedd-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8aedd-127">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8aedd-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageFilter`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8aedd-128">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8aedd-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="8aedd-129">Para compilar la solución, siga las instrucciones de Creación de [ejemplos](../../../../docs/framework/wcf/samples/building-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="8aedd-129">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="8aedd-130">Para ejecutar el ejemplo en una configuración de un solo equipo, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="8aedd-130">To run the sample in a single-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
3. <span data-ttu-id="8aedd-131">Para ejecutar el ejemplo en una configuración entre equipos, siga las instrucciones de Ejecución de los ejemplos de [Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md) y cambie la línea siguiente en Client.cs.</span><span class="sxs-lookup"><span data-stu-id="8aedd-131">To run the sample in a cross-machine configuration, follow the instructions at [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md) and change the following line in Client.cs.</span></span>  
  
    ```csharp
    Uri serviceVia = new Uri("http://localhost/ServiceModelSamples/service.svc");  
    ```  
  
     <span data-ttu-id="8aedd-132">Reemplace el localhost con el nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="8aedd-132">Replace localhost with the name of server.</span></span>  
  
    ```csharp
    Uri serviceVia = new Uri("http://servermachinename/ServiceModelSamples/service.svc");  
    ```  
