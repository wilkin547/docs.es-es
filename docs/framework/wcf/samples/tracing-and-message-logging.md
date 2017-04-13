---
title: "Seguimiento y registro de mensajes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Seguimiento y registro"
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
caps.latest.revision: 53
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 53
---
# Seguimiento y registro de mensajes
Este ejemplo muestra cómo habilitar el seguimiento y registro de mensajes.Los rastros resultantes y registros de mensajes se ven utilizando [Herramienta del visor de seguimiento de servicio \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).Este ejemplo se basa en el [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  El procedimiento de configuración y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
## Seguimiento  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utiliza el mecanismo de la traza definido en el espacio de nombres <xref:System.Diagnostics>.Los orígenes de seguimiento que las aplicaciones implementan generan la información de seguimiento en este modelo de seguimiento.Un nombre identifica cada origen.Los consumidores de seguimiento crean los agentes de escucha de seguimiento para los orígenes de seguimiento para los que desean recuperar información.Debe crear un agente de escucha para que el origen de seguimiento reciba la información de seguimiento.En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], esto se puede hacer agregando el código siguiente al archivo de configuración del servicio o a la configuración del cliente estableciendo el Modelo de servicio de origen de seguimiento `switchValue`:  
  
```  
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
  
 Para obtener más información sobre los orígenes de seguimiento, consulte la sección Origen de seguimiento en el tema [Configurar seguimiento](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).  
  
## Seguimiento de actividad y propagación  
 Tener `ActivityTracing` habilitado y `propagateActivity` establecido en `true` en los orígenes del seguimiento `system.ServiceModel` para el cliente y el servicio proporciona correlación de rastros dentro de las unidades lógicas de procesamiento \(actividades\), a través de las actividades dentro de los extremos \(a través de las transferencias de actividad\), y a través de las actividades que abarcan varios extremos \(a través de la propagación del identificador de actividad\).  
  
 Estos tres mecanismos \(actividades, transferencias y propagación\) pueden ayudarle a buscar la causa principal de un error más rápidamente utilizando Service Trace Viewer tool.Para obtener más información, consulte [Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 Es posible extender la traza que proporciona el ServiceModel al crear los rastros de actividad definidos por el usuario.El seguimiento de la actividad definido por el usuario le permite al usuario crear las actividades de seguimiento para:  
  
-   Agrupar rastros en las unidades lógicas de trabajo.  
  
-   Poner en correlación las actividades a través de las transferencias y la propagación.  
  
-   Disminuya el coste de rendimiento de traza [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] \(por ejemplo, el coste del espacio en disco de un archivo de registro\).  
  
 Para obtener más información sobre seguimiento de actividad definido por el usuario, vea el ejemplo [Extensión del seguimiento](../../../../docs/framework/wcf/samples/extending-tracing.md).  
  
## Registro de mensajes  
 El registro de mensajes puede estar habilitado tanto en el cliente, como en el servicio de cualquier aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Para habilitar el registro de mensajes, debe agregar el código siguiente al cliente o servicio:  
  
```  
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
  
 Cuando se graba un mensaje, el tipo de seguimiento depende de si se sigue paso a paso en el cliente o en el servidor.Por ejemplo, un mensaje "Agregar" que se envía a un cliente se sigue paso a paso bajo la categoría "TransportWrite" en el cliente, mientras que el mismo mensaje se sigue paso a paso bajo la categoría "TransportRead" en el servicio.  
  
 Configurar el agente de escucha de seguimiento agregando el código siguiente a la sección <xref:System.Diagnostics> del archivo App.config del cliente o el archivo Web.config del servicio:  
  
```  
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
>  Los archivos de traza no se crean sin crear inicialmente el directorio de registro.Asegurarse de que el directorio C:\\logs\\ existe, o especifique un directorio de registro alternativo en la configuración del agente de escucha.Vea las instrucciones de configuración preliminar al final de este documento para obtener más información.  
  
 Para obtener más información sobre el registro de mensajes, consulte el tema [Configuración del registro de mensajes](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md).  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado el [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Antes de ejecutar el ejemplo del Registro de mensajes y del seguimiento, cree el directorio C:\\logs\\ para que el servicio escriba los archivos .svc.El nombre de este directorio se define en el archivo de configuración como la ruta de acceso para los rastros y los mensajes que han de registrarse y que pueden cambiarse.Indique el acceso de escritura Network Service del usuario al directorio de registros.  
  
3.  Para compilar la edición de C\#, C\+\+ o Visual Basic .NET de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## Vea también  
 [Seguimiento](../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Ejemplos de supervisión de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)