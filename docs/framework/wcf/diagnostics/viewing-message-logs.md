---
description: 'Más información sobre: Ver registros de mensajes'
title: Visualización de registros de mensajes
ms.date: 03/30/2017
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
ms.openlocfilehash: c640b2c3793839be4a31123701865fa944eaebc8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99758039"
---
# <a name="viewing-message-logs"></a><span data-ttu-id="a8a21-103">Visualización de registros de mensajes</span><span class="sxs-lookup"><span data-stu-id="a8a21-103">Viewing Message Logs</span></span>

<span data-ttu-id="a8a21-104">En este tema se explica cómo puede ver registros de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a8a21-104">This topic describes how you can view message logs.</span></span>  
  
## <a name="viewing-message-logs-in-the-service-trace-viewer"></a><span data-ttu-id="a8a21-105">Visualización de registros de mensajes en Service Trace Viewer</span><span class="sxs-lookup"><span data-stu-id="a8a21-105">Viewing Message Logs in the Service Trace Viewer</span></span>  

 <span data-ttu-id="a8a21-106">Un mensaje se transformará cuando sea procesado por WCF.</span><span class="sxs-lookup"><span data-stu-id="a8a21-106">A message will be transformed as it is processed by WCF.</span></span> <span data-ttu-id="a8a21-107">Por consiguiente, un mensaje que se está registrando refleja solo el contenido del mensaje en el punto en el que se registró, no el contenido en la conexión.</span><span class="sxs-lookup"><span data-stu-id="a8a21-107">Therefore, a message being logged reflects only the message's content at the point it was logged, not the content on the wire.</span></span>  
  
 <span data-ttu-id="a8a21-108">Dado que el resultado del registro de mensajes no está relacionado con el formato de transferencia del mensaje, el registro de mensajes siempre tiene como resultado el mensaje decodificado.</span><span class="sxs-lookup"><span data-stu-id="a8a21-108">Since the output of message logging has no relationship to the transfer format of the message, message logging always outputs the decoded message.</span></span> <span data-ttu-id="a8a21-109">Si se configura correctamente el registro de mensajes, cualquier mensaje registrado debe estar en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="a8a21-109">If you have configured message logging properly, any logged message should be in plain text.</span></span> <span data-ttu-id="a8a21-110">Por ejemplo, el formato (texto sin formato) de los mensajes registrados no se ve afectado por la utilización de un codificador de mensajes binarios.</span><span class="sxs-lookup"><span data-stu-id="a8a21-110">For example, the format (plain text) of the logged messages is not affected by the usage of a binary message encoder.</span></span>  
  
 <span data-ttu-id="a8a21-111">El resultado de XmlWriterTraceListener es un archivo que contiene una secuencia de fragmentos XML.</span><span class="sxs-lookup"><span data-stu-id="a8a21-111">The output of the XmlWriterTraceListener is a file that contains a sequence of XML fragments.</span></span> <span data-ttu-id="a8a21-112">Debería saber que el archivo no es un archivo XML válido.</span><span class="sxs-lookup"><span data-stu-id="a8a21-112">You should be aware that the file is not a valid XML file.</span></span> <span data-ttu-id="a8a21-113">Se recomienda utilizar la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) para ver los archivos de registro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a8a21-113">It is recommended that you use the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) to view the message log files.</span></span> <span data-ttu-id="a8a21-114">Para obtener más información sobre cómo usar esta herramienta, vea el tema sobre cómo usar el [visor de seguimiento de servicios para ver seguimientos correlacionados y solución de problemas](./tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="a8a21-114">For more information on how to use this tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](./tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="a8a21-115">En el visor de seguimiento de servicio, los mensajes se muestran en la pestaña **mensaje** . Los mensajes que han provocado o están relacionados con, un error de procesamiento se resaltan en amarillo (nivel de advertencia) o rojo (nivel de error), dependiendo de la gravedad del error.</span><span class="sxs-lookup"><span data-stu-id="a8a21-115">In the Service Trace Viewer, messages are listed in the **Message** tab. Messages that have caused, or are related to, a processing error are highlighted in yellow (warning level) or red (error level), depending on the severity of the error.</span></span> <span data-ttu-id="a8a21-116">Al hacer doble clic en el mensaje se muestra el seguimiento del mensaje en el contexto de la solicitud de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a8a21-116">Double-clicking on the message brings up the message trace in the context of the processing request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8a21-117">Si un mensaje no tiene encabezado, no se registra ninguna etiqueta `<header/>`.</span><span class="sxs-lookup"><span data-stu-id="a8a21-117">If a message has no header, no `<header/>` tag is logged.</span></span>  
  
## <a name="viewing-messages-logged-by-a-client-a-relay-and-a-service"></a><span data-ttu-id="a8a21-118">Visualización de los mensajes registrados por un cliente, un relé y un servicio</span><span class="sxs-lookup"><span data-stu-id="a8a21-118">Viewing Messages Logged by a Client, a Relay, and a Service</span></span>  

 <span data-ttu-id="a8a21-119">Su entorno puede contener un cliente, que envía un mensaje a un relé, que seguidamente reenvía el mensaje al servicio.</span><span class="sxs-lookup"><span data-stu-id="a8a21-119">Your environment may contain a client, which sends a message to a relay, that subsequently forwards the message to the service.</span></span> <span data-ttu-id="a8a21-120">Cuando el registro de mensajes está habilitado en las tres ubicaciones, y los tres registros de mensajes se ven en la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) simultáneamente, los intercambios de registro de mensajes se representarán incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="a8a21-120">When message logging is enabled on all three locations, and all three message logs are viewed in [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) simultaneously, the message log exchanges will be incorrectly rendered.</span></span> <span data-ttu-id="a8a21-121">Esto se debe a que `CorrelationId` y `ActivityId` en el encabezado del mensaje no son únicos para cada par de envío-recepción.</span><span class="sxs-lookup"><span data-stu-id="a8a21-121">This is because the `CorrelationId` and `ActivityId` in the Message header are not unique for every send-receive pair.</span></span>  
  
 <span data-ttu-id="a8a21-122">Para solucionar este problema puede usar uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8a21-122">You can use either one of the following methods to resolve this problem.</span></span>  
  
- <span data-ttu-id="a8a21-123">Vea solo dos de los tres registros de mensajes en la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="a8a21-123">Only view two of the three message logs in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) at any time.</span></span>  
  
- <span data-ttu-id="a8a21-124">Si debe ver los tres registros en la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) al mismo tiempo, puede modificar el servicio de retransmisión mediante la creación de una nueva <xref:System.ServiceModel.Channels.Message> instancia.</span><span class="sxs-lookup"><span data-stu-id="a8a21-124">If you must view all three logs in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) at the same time, you can modify the relay service by creating a new <xref:System.ServiceModel.Channels.Message> instance.</span></span> <span data-ttu-id="a8a21-125">Esta instancia debería ser una copia del cuerpo del mensaje entrante, más todos los encabezados salvo los encabezados `ActivityId` y `Action`.</span><span class="sxs-lookup"><span data-stu-id="a8a21-125">This instance should be a copy of the body of the incoming message, plus all the headers except for the `ActivityId` and `Action` headers.</span></span> <span data-ttu-id="a8a21-126">En el ejemplo siguiente de código se muestra cómo hacer esto:</span><span class="sxs-lookup"><span data-stu-id="a8a21-126">The following example code demonstrates how to do this.</span></span>  
  
```csharp
Message outgoingMessage = Message.CreateMessage(incomingMessage.Version, incomingMessage.Headers.Action, incomingMessage.GetReaderAtBodyContents());  
  
for (int i = 0; i < incomingMessage.Headers.Count; i++)  
{  
   if (incomingMessage.Headers[i].Name.Equals("ActivityId", StringComparison.InvariantCultureIgnoreCase) ||  
incomingMessage.Headers[i].Name.Equals("Action", StringComparison.InvariantCultureIgnoreCase))  
   {  
      continue;  
    }  
    outgoingMessage.Headers.CopyHeaderFrom(incomingMessage, i);  
}  
```  
  
## <a name="exceptional-cases-for-inaccurate-message-logging-content"></a><span data-ttu-id="a8a21-127">Casos excepcionales de contenido del registro de mensajes inexacto</span><span class="sxs-lookup"><span data-stu-id="a8a21-127">Exceptional Cases for Inaccurate Message Logging Content</span></span>  

 <span data-ttu-id="a8a21-128">Bajo las condiciones siguientes, los mensajes que se están registrados puede que no sean la representación exacta de la presente secuencia de octeto en la conexión.</span><span class="sxs-lookup"><span data-stu-id="a8a21-128">Under the following conditions, messages being logged might not be the exact representation of the octet stream present on the wire.</span></span>  
  
- <span data-ttu-id="a8a21-129">Para BasicHttpBinding, los encabezados de envoltura se registran para los mensajes entrantes en el espacio de nombres /direccionamiento/ninguno.</span><span class="sxs-lookup"><span data-stu-id="a8a21-129">For BasicHttpBinding, envelope headers are logged for the incoming messages in the /addressing/none namespace.</span></span>  
  
- <span data-ttu-id="a8a21-130">Los espacios en blanco pueden no coincidir.</span><span class="sxs-lookup"><span data-stu-id="a8a21-130">White spaces can be mismatched.</span></span>  
  
- <span data-ttu-id="a8a21-131">Para los mensajes entrantes, los elementos vacíos se pueden representar de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="a8a21-131">For incoming messages, empty elements can be represented differently.</span></span> <span data-ttu-id="a8a21-132">Por ejemplo, \<tag> \</tag> en lugar de\<tag/></span><span class="sxs-lookup"><span data-stu-id="a8a21-132">For example, \<tag>\</tag> instead of  \<tag/></span></span>  
  
- <span data-ttu-id="a8a21-133">Cuando el registro de PII conocido está deshabilitado de forma predeterminada o explícita estableciendo enableLoggingKnownPii="true".</span><span class="sxs-lookup"><span data-stu-id="a8a21-133">When known PII logging is disabled either by default or explicit setting enableLoggingKnownPii="true".</span></span>  
  
- <span data-ttu-id="a8a21-134">La codificación se habilita para transformar a UTF-8.</span><span class="sxs-lookup"><span data-stu-id="a8a21-134">Encoding is enabled for transforming to UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8a21-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8a21-135">See also</span></span>

- [<span data-ttu-id="a8a21-136">Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="a8a21-136">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../service-trace-viewer-tool-svctraceviewer-exe.md)
- [<span data-ttu-id="a8a21-137">Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="a8a21-137">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](./tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="a8a21-138">Registro de mensajes</span><span class="sxs-lookup"><span data-stu-id="a8a21-138">Message Logging</span></span>](message-logging.md)
