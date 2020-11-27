---
title: Configurar la traza de flujo de mensajes
ms.date: 03/30/2017
ms.assetid: 15571ca2-bee2-47fb-ba10-fcbc09152ad0
ms.openlocfilehash: 6c271c26eb4e57014b3aaebf306b283bd06c7119
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254888"
---
# <a name="configuring-message-flow-tracing"></a><span data-ttu-id="e8185-102">Configurar la traza de flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="e8185-102">Configuring Message Flow Tracing</span></span>

<span data-ttu-id="e8185-103">Cuando está habilitada la traza de la actividad Windows Communication Foundation (WCF), los identificadores de actividad de un extremo a otro se asignan a las actividades lógicas en toda la pila de WCF.</span><span class="sxs-lookup"><span data-stu-id="e8185-103">When Windows Communication Foundation (WCF) activity tracing is enabled, End-To-End Activity IDs are assigned to logical activities throughout the WCF stack.</span></span> <span data-ttu-id="e8185-104">En [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)], hay ahora una versión con un rendimiento más alto de esta característica que funciona con Seguimiento de eventos para Windows (ETW) denominada traza de flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e8185-104">In [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)], there is now a higher performance version of this feature that works with Event Tracing for Windows (ETW) called message flow tracing.</span></span> <span data-ttu-id="e8185-105">Cuando se habilita, los identificadores de actividad de un extremo a otro se toman (o se asignan si están vacíos) de los mensajes entrantes y se propagan a todos los eventos de traza que se emiten una vez que el canal ha descodificado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e8185-105">When enabled, End-To-End activity IDs are taken from (or assigned to if empty) incoming messages and are propagated to all tracing events that are emitted after the message has been decoded by the channel.</span></span> <span data-ttu-id="e8185-106">Los clientes pueden utilizar esta característica para reconstruir flujos de mensajes con registros de seguimiento de distintos servicios tras la descodificación.</span><span class="sxs-lookup"><span data-stu-id="e8185-106">Customers can use this feature to reconstruct message flows with trace logs from different services after decoding.</span></span>  
  
 <span data-ttu-id="e8185-107">Se puede habilitar la traza al detectar un problema con la aplicación y, a continuación, deshabilitarla una vez resuelto el problema.</span><span class="sxs-lookup"><span data-stu-id="e8185-107">Tracing can be enabled after a problem is detected with the application and then disabled once the problem is resolved.</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="e8185-108">La habilitación del seguimiento</span><span class="sxs-lookup"><span data-stu-id="e8185-108">Enabling Tracing</span></span>  

 <span data-ttu-id="e8185-109">Puede habilitar la traza del flujo de mensajes estableciendo el elemento de configuración `messageFlowTracing` de .NET Framework 4 como `true`, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e8185-109">You can enable message flow tracing by setting the .NET Framework 4 `messageFlowTracing` configuration element to `true`, as shown in the following example.</span></span>  
  
```xml  
<system.servicemodel>  
  <diagnostics>  
    <endToEndTracing propagateActivity="true" messageFlowTracing="true" />  
  </diagnostics>  
</system.servicemodel>  
```  
  
> [!NOTE]
> <span data-ttu-id="e8185-110">Dado que el elemento de configuración `endToEndTracing` reside en un archivo Web.config, no se puede configurar dinámicamente de la misma manera que ETW.</span><span class="sxs-lookup"><span data-stu-id="e8185-110">Because the `endToEndTracing` configuration element resides in a Web.config file, it cannot be dynamically configured in the same way as ETW.</span></span> <span data-ttu-id="e8185-111">Para que el elemento de configuración `endToEndTracing` surta efecto, hay que reciclar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e8185-111">For the `endToEndTracing` configuration element to take effect, the application must be recycled.</span></span>  
  
 <span data-ttu-id="e8185-112">Las actividades se correlacionan mediante el intercambio de un identificador denominado de actividad.</span><span class="sxs-lookup"><span data-stu-id="e8185-112">Activities are correlated by the interchange of an identifier called the activity ID.</span></span> <span data-ttu-id="e8185-113">Este identificador es un GUID y lo genera la clase System.Diagnostics.CorrelationManager.</span><span class="sxs-lookup"><span data-stu-id="e8185-113">This identifier is a GUID, and is generated by the System.Diagnostics.CorrelationManager class.</span></span> <span data-ttu-id="e8185-114">Si manipula el System.Diagnostics.Trace.CorrelationManager.ActivityID, asegúrese de que el valor se establece en el valor original cuando el control de la ejecución se vuelve a transferir al código WCF.</span><span class="sxs-lookup"><span data-stu-id="e8185-114">If you manipulate System.Diagnostics.Trace.CorrelationManager.ActivityID, ensure that the value is set to original when execution control transfers back to WCF code.</span></span>  <span data-ttu-id="e8185-115">Además, si usa un modelo de programación WCF asincrónico, se asegura de que el System.Diagnostics.Trace.CorrelationManager.ActivityID se transfiere entre los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="e8185-115">Also, if you use an asynchronous WCF programming model ensure that System.Diagnostics.Trace.CorrelationManager.ActivityID is transferred between the threads.</span></span>  
  
## <a name="message-flow-tracing-and-rest-services"></a><span data-ttu-id="e8185-116">Seguimiento de flujo de mensajes y servicios REST</span><span class="sxs-lookup"><span data-stu-id="e8185-116">Message Flow Tracing and REST Services</span></span>  

 <span data-ttu-id="e8185-117">El seguimiento de flujo de mensajes permite realizar un seguimiento a una solicitud extremo a extremo.</span><span class="sxs-lookup"><span data-stu-id="e8185-117">Message flow tracing allows you to trace a request end to end.</span></span>  <span data-ttu-id="e8185-118">Con servicios basados en SOAP- se envía un Id. de actividad en un encabezado de mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="e8185-118">With SOAP-based services an Activity ID is sent in a SOAP message header.</span></span> <span data-ttu-id="e8185-119">Las solicitudes REST no contienen este encabezado, por ello se usa un encabezado especial de eventos HTTP en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e8185-119">REST requests do not contain this header so a special HTTP event header is used instead.</span></span> <span data-ttu-id="e8185-120">El fragmento de código siguiente muestra cómo se puede recuperar mediante programación el valor de Id. de actividad:</span><span class="sxs-lookup"><span data-stu-id="e8185-120">The following code snippet shows how you can programmatically retrieve the Activity ID value:</span></span>  
  
```csharp
Object output = null;
if (OperationContext.Current.IncomingMessageProperties.TryGetValue(HttpRequestMessageProperty.Name, out output))
{
   HttpRequestMessageProperty httpHeaders = output as HttpRequestMessageProperty;
   // Retrieve the Activity Id from the HTTP header    string e2eId = httpHeaders.Headers["E2EActivity"];
   // ...
}
```

 <span data-ttu-id="e8185-121">Puede agregar el encabezado mediante programación usando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8185-121">You can programmatically add the header using the following code:</span></span>  
  
```csharp  
HttpContent content = new StreamContent(contentStream);  
Guid correlation = Guid.NewGuid();  
content.Headers.Add("E2EActivity", Convert.ToBase64String(correlation.ToByteArray()));  
```
