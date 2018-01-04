---
title: Seguimiento y registro de mensajes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
caps.latest.revision: "53"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 91d824efaf8f58074297c417990ecf6b3aef78eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="tracing-and-message-logging"></a>Seguimiento y registro de mensajes
Este ejemplo muestra cómo habilitar el seguimiento y registro de mensajes. Los registros de mensajes y seguimientos resultantes se ven mediante la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
## <a name="tracing"></a>Traza  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utiliza el mecanismo de la traza definido en el espacio de nombres <xref:System.Diagnostics>. Los orígenes de seguimiento que las aplicaciones implementan generan la información de seguimiento en este modelo de seguimiento. Un nombre identifica cada origen. Los consumidores de seguimiento crean los agentes de escucha de seguimiento para los orígenes de seguimiento para los que desean recuperar información. Debe crear un agente de escucha para que el origen de seguimiento reciba la información de seguimiento. En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], esto se puede hacer agregando el código siguiente al archivo de configuración del servicio o a la configuración del cliente estableciendo el Modelo de servicio de origen de seguimiento `switchValue`:  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-service.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 Para obtener más información acerca de los orígenes de seguimiento, vea la sección origen de seguimiento en el [configurar el seguimiento](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) tema.  
  
## <a name="activity-tracing-and-propagation"></a>Seguimiento de actividad y propagación  
 Tener `ActivityTracing` habilitado y `propagateActivity` establecido en `true` en el `system.ServiceModel` orígenes de seguimiento para el cliente y el servicio proporcionan correlación de seguimientos en unidades lógicas de procesamiento (actividades), a través de las actividades dentro de los puntos de conexión ( a través de las transferencias de actividad) y a través de las actividades que abarcan varios puntos de conexión (a través de la propagación del identificador de actividad).  
  
 Estos tres mecanismos (actividades, transferencias y propagación) pueden ayudarle a buscar la causa principal de un error más rápidamente utilizando Service Trace Viewer tool. Para obtener más información, consulte [utilizando Service Trace Viewer para ver los seguimientos correlacionados y solución de problemas](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 Es posible extender la traza que proporciona el ServiceModel al crear los rastros de actividad definidos por el usuario. El seguimiento de la actividad definido por el usuario le permite al usuario crear las actividades de seguimiento para:  
  
-   Agrupar rastros en las unidades lógicas de trabajo.  
  
-   Poner en correlación las actividades a través de las transferencias y la propagación.  
  
-   Disminuya el coste de rendimiento de traza [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (por ejemplo, el coste del espacio en disco de un archivo de registro).  
  
 Para obtener más información sobre el seguimiento de actividad definido por el usuario, consulte la [extender seguimiento](../../../../docs/framework/wcf/samples/extending-tracing.md) ejemplo.  
  
## <a name="message-logging"></a>Registro de mensajes  
 El registro de mensajes puede estar habilitado tanto en el cliente, como en el servicio de cualquier aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Para habilitar el registro de mensajes, debe agregar el código siguiente al cliente o servicio:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics>  
      <!-- Enable Message Logging here. -->  
      <!-- log all messages received or sent at the transport or service model levels >  
      <messageLogging logEntireMessage="true"  
                      maxMessagesToLog="300"  
                      logMessagesAtServiceLevel="true"  
                      logMalformedMessages="true"  
                      logMessagesAtTransportLevel="true" />  
    </diagnostics>  
  </system.serviceModel>  
</configuration>  
```  
  
 Cuando se graba un mensaje, el tipo de seguimiento depende de si se sigue paso a paso en el cliente o en el servidor. Por ejemplo, un mensaje "Agregar" que se envía a un cliente se sigue paso a paso bajo la categoría "TransportWrite" en el cliente, mientras que el mismo mensaje se sigue paso a paso bajo la categoría "TransportRead" en el servicio.  
  
 Configurar el agente de escucha de seguimiento agregando el código siguiente a la sección <xref:System.Diagnostics> del archivo App.config del cliente o el archivo Web.config del servicio:  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-client.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
```  
  
 Los mensajes están registrados en formato XML en el directorio de destino especificado en el archivo de configuración.  
  
> [!NOTE]
>  Los archivos de traza no se crean sin crear inicialmente el directorio de registro. Asegurarse de que el directorio C:\logs\ existe, o especifique un directorio de registro alternativo en la configuración del agente de escucha. Vea las instrucciones de configuración preliminar al final de este documento para obtener más información.  
  
 Para obtener más información sobre el registro de mensajes, consulte el [configuración de registro de mensajes](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) tema.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Antes de ejecutar el ejemplo del Registro de mensajes y del seguimiento, cree el directorio C:\logs\ para que el servicio escriba los archivos .svc. El nombre de este directorio se define en el archivo de configuración como la ruta de acceso para los rastros y los mensajes que han de registrarse y que pueden cambiarse. Indique el acceso de escritura Network Service del usuario al directorio de registros.  
  
3.  Para compilar el C#, C++ o Visual Basic .NET edition de la solución, siga las instrucciones que aparecen en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración de equipo único o varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a>Vea también  
 [Traza](../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Ejemplos de supervisión de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
