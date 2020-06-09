---
title: Propagación
ms.date: 03/30/2017
ms.assetid: f8181e75-d693-48d1-b333-a776ad3b382a
ms.openlocfilehash: 732ae5cb1ce311b78728f8d5de0fd9102bf32499
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578960"
---
# <a name="propagation"></a><span data-ttu-id="653f8-102">Propagación</span><span class="sxs-lookup"><span data-stu-id="653f8-102">Propagation</span></span>
<span data-ttu-id="653f8-103">En este tema se describe la propagación de actividades en el modelo de seguimiento de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="653f8-103">This topic describes activity propagation in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
## <a name="using-propagation-to-correlate-activities-across-endpoints"></a><span data-ttu-id="653f8-104">Utilización de la propagación para poner en correlación actividades entre los puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="653f8-104">Using Propagation to Correlate Activities Across Endpoints</span></span>  
 <span data-ttu-id="653f8-105">La propagación proporciona al usuario la correlación directa de las trazas de error de la misma unidad de procesamiento, entre los puntos de conexión de la aplicación, p. ej., una solicitud.</span><span class="sxs-lookup"><span data-stu-id="653f8-105">Propagation provides the user with direct correlation of error traces for the same unit of processing across application endpoints, for example, a request.</span></span> <span data-ttu-id="653f8-106">Los errores emitidos en diferentes puntos de conexión de la misma unidad de procesamiento se agrupan en la misma actividad, incluso en todos los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="653f8-106">Errors emitted at different endpoints for the same unit of processing are grouped in the same activity, even across application domains.</span></span> <span data-ttu-id="653f8-107">Esto se realiza a través de la propagación del id. de actividad en los encabezados del mensaje.</span><span class="sxs-lookup"><span data-stu-id="653f8-107">This is done through propagation of the activity ID in the message headers.</span></span> <span data-ttu-id="653f8-108">Por lo tanto, si a un cliente se le agota el tiempo de espera debido a un error interno del servidor, ambos errores aparecen en la misma actividad para una correlación directa.</span><span class="sxs-lookup"><span data-stu-id="653f8-108">Therefore, if a client times out because of an internal error in the server, both errors appear in the same activity for direct correlation.</span></span>  
  
 <span data-ttu-id="653f8-109">Para ello, utilice el valor `ActivityTracing` como se mostró en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="653f8-109">To do this, use the `ActivityTracing` setting as demonstrated in the previous example.</span></span> <span data-ttu-id="653f8-110">Además, establezca el atributo `propagateActivity` para el origen de seguimiento de traza `System.ServiceModel` en todos los extremos.</span><span class="sxs-lookup"><span data-stu-id="653f8-110">In addition, set the `propagateActivity` attribute for the `System.ServiceModel` trace source at all endpoints.</span></span>  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing" propagateActivity="true" >  
```  
  
 <span data-ttu-id="653f8-111">La propagación de actividades es una capacidad configurable que hace que WCF agregue un encabezado a los mensajes salientes, que incluye el identificador de actividad en el TLS.</span><span class="sxs-lookup"><span data-stu-id="653f8-111">Activity propagation is a configurable capability that causes WCF to add a header to outbound messages, which includes the activity ID on the TLS.</span></span> <span data-ttu-id="653f8-112">Mediante la inclusión de este dato en las trazas subsiguientes en el lado del servidor, se pueden poner en correlación las actividades del cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="653f8-112">By including this on subsequent traces on the server side, we can correlate client and server activities.</span></span>  
  
## <a name="propagation-definition"></a><span data-ttu-id="653f8-113">Definición de propagación</span><span class="sxs-lookup"><span data-stu-id="653f8-113">Propagation Definition</span></span>  
 <span data-ttu-id="653f8-114">El gAId de la actividad M se propaga a la actividad N si se aplican todas las condiciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="653f8-114">Activity M’s gAId is propagated to activity N if all of the following conditions apply.</span></span>  
  
- <span data-ttu-id="653f8-115">N se creó debido a M</span><span class="sxs-lookup"><span data-stu-id="653f8-115">N is created because of M</span></span>  
  
- <span data-ttu-id="653f8-116">N conoce el gAId de M</span><span class="sxs-lookup"><span data-stu-id="653f8-116">M’s gAId is known to N</span></span>  
  
- <span data-ttu-id="653f8-117">El gAId de N es igual al gAId de M.</span><span class="sxs-lookup"><span data-stu-id="653f8-117">N's gAId is equal to M’s gAId.</span></span>  
  
 <span data-ttu-id="653f8-118">El gAId se propaga a través del encabezado del mensaje de ActivityId, como se muestra en el siguiente esquema XML.</span><span class="sxs-lookup"><span data-stu-id="653f8-118">The gAId is propagated through the ActivityId message header, as illustrated in the following XML schema.</span></span>  
  
```xml  
<xsd:element name="ActivityId" type="integer" minOccurs="0">  
  <xsd:attribute name="CorrelationId" type="integer" minOccurs="0"/>  
</xsd:element>  
```  
  
 <span data-ttu-id="653f8-119">A continuación se muestra un ejemplo del encabezado del mensaje:</span><span class="sxs-lookup"><span data-stu-id="653f8-119">The following is an example of the message header.</span></span>  
  
```xml  
<MessageLogTraceRecord>  
  <s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope"
                      xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      <a:Action s:mustUnderstand="1">http://Microsoft.ServiceModel.Samples/ICalculator/Subtract  
      </a:Action>  
      <a:MessageID>urn:uuid:f0091eae-d339-4c7e-9408-ece34602f1ce  
      </a:MessageID>  
      <ActivityId CorrelationId="f94c6af1-7d5d-4295-b693-4670a8a0ce34"
               xmlns="http://schemas.microsoft.com/2004/09/ServiceModel/Diagnostics">  
        17f59a29-b435-4a15-bf7b-642ffc40eac8  
      </ActivityId>  
      <a:ReplyTo>  
          <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
      </a:ReplyTo>  
      <a:To s:mustUnderstand="1">net.tcp://localhost/servicemodelsamples/service</a:To>  
   </s:Header>  
   <s:Body>  
     <Subtract xmlns="http://Microsoft.ServiceModel.Samples">  
       <n1>145</n1>  
       <n2>76.54</n2>  
     </Subtract>  
   </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
```  
  
## <a name="propagation-and-activity-boundaries"></a><span data-ttu-id="653f8-120">Límites de la propagación y la actividad</span><span class="sxs-lookup"><span data-stu-id="653f8-120">Propagation and Activity Boundaries</span></span>  
 <span data-ttu-id="653f8-121">Cuando el identificador de actividad se propaga por los puntos de conexión, el receptor del mensaje emite trazas de inicio y detención con ese identificador de actividad (propagado).</span><span class="sxs-lookup"><span data-stu-id="653f8-121">When the activity ID is propagated across endpoints, the message receiver emits a Start and Stop traces with that (propagated) activity ID.</span></span> <span data-ttu-id="653f8-122">Por lo tanto, existe una traza de inicio y una de detención con el gAId de cada origen de seguimiento de traza.</span><span class="sxs-lookup"><span data-stu-id="653f8-122">Therefore, there is a Start and Stop trace with that gAId from each trace source.</span></span> <span data-ttu-id="653f8-123">Si los puntos de conexión están en el mismo proceso y utilizan el mismo nombre de origen de seguimiento, se crean varios inicios y detenciones con el mismo gAId (mismo gAId, mismo origen de seguimiento, mismo proceso).</span><span class="sxs-lookup"><span data-stu-id="653f8-123">If the endpoints are in the same process and use the same trace source name, multiple Start and Stop with the same lAId (same gAId, same trace source, same process) are created.</span></span>  
  
## <a name="synchronization"></a><span data-ttu-id="653f8-124">Sincronización</span><span class="sxs-lookup"><span data-stu-id="653f8-124">Synchronization</span></span>  
 <span data-ttu-id="653f8-125">Para sincronizar los eventos a través de los puntos de conexión que se ejecutan en distintos equipos, CorrelationId se agrega al encabezado de ActivityId que se propaga en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="653f8-125">To synchronize events across endpoints that run on different machines, a CorrelationId is added to the ActivityId header that is propagated in messages.</span></span> <span data-ttu-id="653f8-126">Las herramientas pueden utilizar este id. para sincronizar eventos entre equipos con discrepancia de reloj.</span><span class="sxs-lookup"><span data-stu-id="653f8-126">Tools can use this ID to synchronize events across machines with clock discrepancy.</span></span> <span data-ttu-id="653f8-127">En concreto, la herramienta Service Trace Viewer utiliza este identificador para mostrar los flujos de mensaje entre los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="653f8-127">Specifically, the Service Trace Viewer tool uses this ID for showing message flows between endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="653f8-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="653f8-128">See also</span></span>

- [<span data-ttu-id="653f8-129">Configurar seguimiento</span><span class="sxs-lookup"><span data-stu-id="653f8-129">Configuring Tracing</span></span>](configuring-tracing.md)
- [<span data-ttu-id="653f8-130">Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="653f8-130">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="653f8-131">Escenarios de seguimiento de traza de un extremo a otro</span><span class="sxs-lookup"><span data-stu-id="653f8-131">End-To-End Tracing Scenarios</span></span>](end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="653f8-132">Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="653f8-132">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
