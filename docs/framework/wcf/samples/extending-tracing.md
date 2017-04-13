---
title: "Extensi&#243;n del seguimiento | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# Extensi&#243;n del seguimiento
Este ejemplo muestra cómo extender la característica de seguimiento de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] escribiendo el seguimiento de la actividad definida por el usuario en el código de cliente y de servicio.Esto permite al usuario crear actividades de seguimiento y seguimientos de grupo en las unidades lógicas de trabajo.También es posible poner en correlación las actividades a través de las transferencias \(dentro del mismo extremo\) y propagación \(a través de los extremos\).En este ejemplo, el seguimiento se habilita para el cliente y el servicio.Para obtener más información acerca de cómo habilitar el seguimiento en los archivos de configuración del cliente y el servicio, vea [Seguimiento y registro de mensajes](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  
  
 Este ejemplo se basa en el [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## Propagación de seguimiento y de actividad  
 El seguimiento de actividad definida por el usuario permite al usuario crear sus propias actividades de seguimiento para agrupar seguimientos en unidades lógicas de trabajo, poner en correlación las actividades a través de transferencias y propagación, y disminuir el costo de rendimiento de la traza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] \(por ejemplo, el costo del espacio en disco de un archivo de registro\).  
  
### Adición de orígenes personalizados  
 Los seguimientos definidos por el usuario pueden añadirse tanto al código de cliente como de servicio.La adición de orígenes de seguimiento a los archivos de configuración de cliente o servicio permiten que los seguimientos personalizados se graben y se muestren en [Herramienta del visor de seguimiento de servicio \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).El código siguiente muestra cómo agregar un origen de seguimiento definido por el usuario denominado `ServerCalculatorTraceSource` al archivo de configuración.  
  
```  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
        <source name="ServerCalculatorTraceSource" switchValue="Information,ActivityTracing">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
       <add initializeData="C:\logs\ServerTraces.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" traceOutputOptions="Callstack">  
            <filter type="" />  
        </add>  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>....  
....  
```  
  
### Cómo poner en correlación las actividades  
 Para poner en correlación directamente las actividades con los extremos, el atributo `propagateActivity` debe estar establecido en `true` en el origen de seguimiento `System.ServiceModel`.Además, para propagar los seguimientos sin pasar por las actividades de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], se debe desactivar el seguimiento de la actividad de ServiceModel.Esto puede verse en el siguiente ejemplo de código:  
  
> [!NOTE]
>  Desactivar el seguimiento de actividades de ServiceModel no es igual que tener el nivel de seguimiento, indicado por la propiedad `switchValue`, definido en desactivado.  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### Disminución del coste de rendimiento  
 Al establecer `ActivityTracing` en desactivado en el origen de seguimiento de `System.ServiceModel`, se genera un archivo de seguimiento que contiene solo seguimientos de actividad definidos por el usuario sin ninguno de los seguimientos de actividad de ServiceModel incluidos.Esto genera un archivo de registro de mucho menor tamaño.Sin embargo, se pierde la oportunidad de poner en correlación los seguimientos de procesamiento de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
##### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado el [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código de la edición .NET de C\# o Visual Basic de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## Vea también  
 [Ejemplos de supervisión de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)