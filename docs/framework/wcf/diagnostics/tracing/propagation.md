---
title: "Propagaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f8181e75-d693-48d1-b333-a776ad3b382a
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Propagaci&#243;n
En este tema se describe la propagación de actividad en [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] el modelo de seguimiento de traza.  
  
## Utilización de la propagación para poner en correlación actividades entre los extremos  
 La propagación proporciona al usuario la correlación directa de las trazas de error de la misma unidad de procesamiento, entre los extremos de la aplicación, p. ej., una solicitud.  Los errores emitidos en diferentes extremos de la misma unidad de procesamiento se agrupan en la misma actividad, incluso en todos los dominios de aplicación.  Esto se realiza a través de la propagación del id. de actividad en los encabezados del mensaje.  Por lo tanto, si a un cliente se le agota el tiempo de espera debido a un error interno del servidor, ambos errores aparecen en la misma actividad para una correlación directa.  
  
 Para ello, utilice el valor `ActivityTracing` como se mostró en el ejemplo anterior.  Además, establezca el atributo `propagateActivity` para el origen de seguimiento de traza `System.ServiceModel` en todos los extremos.  
  
```  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing" propagateActivity=”true” >  
```  
  
 La propagación de actividad es una función que puede configurarse y que provoca que [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] agregue un encabezado a los mensajes salientes, en el que se incluye el id. de actividad de la TLS.  Mediante la inclusión de este dato en las trazas subsiguientes en el lado del servidor, se pueden poner en correlación las actividades del cliente y el servidor.  
  
## Definición de propagación  
 El gAId de la actividad M se propaga a la actividad N si se aplican todas las condiciones siguientes.  
  
-   N se creó debido a M  
  
-   N conoce el gAId de M  
  
-   El gAId de N es igual al gAId de M.  
  
 El gAId se propaga a través del encabezado del mensaje de ActivityId, como se muestra en el siguiente esquema XML.  
  
```  
<xsd:element name=”ActivityId” type=”integer” minOccurs=”0”>  
  <xsd:attribute name=”CorrelationId” type=”integer” minOccurs=”0”/>  
</xsd:element>  
```  
  
 A continuación se muestra un ejemplo del encabezado del mensaje:  
  
```  
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
          <a:Address>http://www.w3.org/2005/08/addressing/anonymous  
          </a:Address>  
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
  
## Límites de la propagación y la actividad  
 Cuando el identificador de actividad se propaga por los extremos, el receptor del mensaje emite trazas de inicio y detención con ese identificador de actividad \(propagado\).  Por lo tanto, existe una traza de inicio y una de detención con el gAId de cada origen de seguimiento de traza.  Si los extremos están en el mismo proceso y utilizan el mismo nombre de origen de seguimiento, se crean varios inicios y detenciones con el mismo gAId \(mismo gAId, mismo origen de seguimiento, mismo proceso\).  
  
## Sincronización  
 Para sincronizar los eventos a través de los extremos que se ejecutan en distintos equipos, CorrelationId se agrega al encabezado de ActivityId que se propaga en los mensajes.  Las herramientas pueden utilizar este id. para sincronizar eventos entre equipos con discrepancia de reloj.  En concreto, la herramienta Service Trace Viewer utiliza este identificador para mostrar los flujos de mensaje entre los extremos.  
  
## Vea también  
 [Configurar seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)   
 [Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)   
 [Escenarios de seguimiento de traza de un extremo a otro](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)   
 [Herramienta del visor de seguimiento de servicio \(SvcTraceViewer.exe\)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)