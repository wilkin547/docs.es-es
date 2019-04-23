---
title: Visualización de registros de mensajes
ms.date: 03/30/2017
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
ms.openlocfilehash: 2322d2a6e0c5a6f26ad103be72230666f6bca191
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139066"
---
# <a name="viewing-message-logs"></a>Visualización de registros de mensajes
En este tema se explica cómo puede ver registros de mensajes.  
  
## <a name="viewing-message-logs-in-the-service-trace-viewer"></a>Visualización de registros de mensajes en Service Trace Viewer  
 Un mensaje se transformará mientras lo procesa por WCF. Por consiguiente, un mensaje que se está registrando refleja solo el contenido del mensaje en el punto en el que se registró, no el contenido en la conexión.  
  
 Dado que el resultado del registro de mensajes no está relacionado con el formato de transferencia del mensaje, el registro de mensajes siempre tiene como resultado el mensaje decodificado. Si se configura correctamente el registro de mensajes, cualquier mensaje registrado debe estar en texto sin formato. Por ejemplo, el formato (texto sin formato) de los mensajes registrados no se ve afectado por la utilización de un codificador de mensajes binarios.  
  
 El resultado de XmlWriterTraceListener es un archivo que contiene una secuencia de fragmentos XML. Debería saber que el archivo no es un archivo XML válido. Se recomienda que utilice el [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) para ver los archivos de registro de mensajes. Para obtener más información sobre cómo usar esta herramienta, consulte [utilizando Service Trace Viewer para ver seguimientos correlacionados y solución de problemas](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 En Service Trace Viewer, los mensajes se muestran en el **mensaje** ficha. Los mensajes que han producido, o están relacionados con un error de procesamiento se resaltan en amarillo (nivel de advertencia) o rojo (nivel del error), dependiendo de la gravedad del error. Al hacer doble clic en el mensaje se muestra el seguimiento del mensaje en el contexto de la solicitud de procesamiento.  
  
> [!NOTE]
>  Si un mensaje no tiene encabezado, no se registra ninguna etiqueta `<header/>`.  
  
## <a name="viewing-messages-logged-by-a-client-a-relay-and-a-service"></a>Visualización de los mensajes registrados por un cliente, un relé y un servicio  
 Su entorno puede contener un cliente, que envía un mensaje a un relé, que seguidamente reenvía el mensaje al servicio. Cuando está habilitado el registro de mensajes en las tres ubicaciones y los tres registros de mensaje se ven en [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) los intercambios del registro de mensajes al mismo tiempo, se representarán incorrectamente. Esto se debe a que `CorrelationId` y `ActivityId` en el encabezado del mensaje no son únicos para cada par de envío-recepción.  
  
 Para solucionar este problema puede usar uno de los métodos siguientes:  
  
-   Ver sólo dos de los tres registros de mensajes en el [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) en cualquier momento.  
  
-   Si ve los tres registros en el [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) al mismo tiempo, puede modificar el servicio de retransmisión mediante la creación de un nuevo <xref:System.ServiceModel.Channels.Message> instancia. Esta instancia debería ser una copia del cuerpo del mensaje entrante, más todos los encabezados salvo los encabezados `ActivityId` y `Action`. En el ejemplo siguiente de código se muestra cómo hacer esto:  
  
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
  
## <a name="exceptional-cases-for-inaccurate-message-logging-content"></a>Casos excepcionales de contenido del registro de mensajes inexacto  
 Bajo las condiciones siguientes, los mensajes que se están registrados puede que no sean la representación exacta de la presente secuencia de octeto en la conexión.  
  
-   Para BasicHttpBinding, los encabezados de envoltura se registran para los mensajes entrantes en el espacio de nombres /direccionamiento/ninguno.  
  
-   Puede que no coincidan los espacios en blanco.  
  
-   Para los mensajes entrantes, los elementos vacíos se pueden representar de manera diferente. Por ejemplo, \<etiqueta >\</etiqueta > en lugar de \<etiqueta / >  
  
-   Cuando el registro de PII conocido está deshabilitado de forma predeterminada o explícita estableciendo enableLoggingKnownPii="true".  
  
-   La codificación se habilita para transformar a UTF-8.  
  
## <a name="see-also"></a>Vea también

- [Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
- [Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Registro de mensajes](../../../../docs/framework/wcf/diagnostics/message-logging.md)
