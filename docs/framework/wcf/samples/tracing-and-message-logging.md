---
title: Seguimiento y registro de mensajes
ms.date: 03/30/2017
helpviewer_keywords:
- Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
ms.openlocfilehash: 9ffb7a99540b953fc93a22d2296caf86f294d25d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143829"
---
# <a name="tracing-and-message-logging"></a>Seguimiento y registro de mensajes
Este ejemplo muestra cómo habilitar el seguimiento y registro de mensajes. Los seguimientos resultantes y los registros de mensajes se ven mediante la herramienta [Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). Este ejemplo se basa en la [introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
## <a name="tracing"></a>Seguimiento  
 Windows Communication Foundation (WCF) usa el <xref:System.Diagnostics> mecanismo de seguimiento definido en el espacio de nombres. Los orígenes de seguimiento que las aplicaciones implementan generan la información de seguimiento en este modelo de seguimiento. Un nombre identifica cada origen. Los consumidores de seguimiento crean los agentes de escucha de seguimiento para los orígenes de seguimiento para los que desean recuperar información. Debe crear un agente de escucha para que el origen de seguimiento reciba la información de seguimiento. En WCF, esto se puede hacer agregando el código siguiente al archivo de configuración del `switchValue`servicio o del cliente estableciendo el origen de seguimiento del modelo de servicio:  
  
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
  
 Para obtener más información acerca de los orígenes de seguimiento, consulte la sección Origen de seguimiento en el tema [Configuración del seguimiento.](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
  
## <a name="activity-tracing-and-propagation"></a>Seguimiento de actividad y propagación  
 Una `ActivityTracing` vez `propagateActivity` habilitado `true` y `system.ServiceModel` establecido en los orígenes de seguimiento para el cliente y el servicio, proporciona la correlación de seguimientos dentro de unidades lógicas de procesamiento (actividades), entre actividades dentro de puntos finales (mediante transferencias de actividad) y entre actividades que abarcan varios puntos de conexión (mediante la propagación de ID de actividad).  
  
 Estos tres mecanismos (actividades, transferencias y propagación) pueden ayudarle a buscar la causa principal de un error más rápidamente utilizando Service Trace Viewer tool. Para obtener más información, consulte Uso del Visor de seguimiento de servicio [para ver seguimientos correlacionados y Solución de problemas](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 Es posible extender la traza que proporciona el ServiceModel al crear los rastros de actividad definidos por el usuario. El seguimiento de la actividad definido por el usuario le permite al usuario crear las actividades de seguimiento para:  
  
- Agrupar rastros en las unidades lógicas de trabajo.  
  
- Poner en correlación las actividades a través de las transferencias y la propagación.  
  
- Disminuya el costo de rendimiento del seguimiento de WCF (por ejemplo, el costo de espacio en disco de un archivo de registro).  
  
 Para obtener más información sobre el seguimiento de actividad definido por el usuario, consulte el [ejemplo Extending Tracing](../../../../docs/framework/wcf/samples/extending-tracing.md) .  
  
## <a name="message-logging"></a>Registro de mensajes  
 El registro de mensajes se puede habilitar tanto en el cliente como en el servicio de cualquier aplicación WCF. Para habilitar el registro de mensajes, debe agregar el código siguiente al cliente o servicio:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics>  
      <!-- Enable Message Logging here. -->  
      <!-- log all messages received or sent at the transport or service model levels -->  
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
> Los archivos de traza no se crean sin crear inicialmente el directorio de registro. Asegurarse de que el directorio C:\logs\ existe, o especifique un directorio de registro alternativo en la configuración del agente de escucha. Vea las instrucciones de configuración preliminar al final de este documento para obtener más información.  
  
 Para obtener más información sobre el registro de mensajes, consulte el tema [Configuración del registro](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) de mensajes.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .  
  
2. Antes de ejecutar el ejemplo del Registro de mensajes y del seguimiento, cree el directorio C:\logs\ para que el servicio escriba los archivos .svc. El nombre de este directorio se define en el archivo de configuración como la ruta de acceso para los rastros y los mensajes que han de registrarse y que pueden cambiarse. Indique el acceso de escritura Network Service del usuario al directorio de registros.  
  
3. Para compilar la edición de la solución de .NET de Visual Basic, siga las instrucciones de Creación de [ejemplos](../../../../docs/framework/wcf/samples/building-the-samples.md)de Windows Communication Foundation .  
  
4. Para ejecutar el ejemplo en una configuración de un equipo o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a>Consulte también

- [Rastreo](../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Ejemplos de supervisión de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
