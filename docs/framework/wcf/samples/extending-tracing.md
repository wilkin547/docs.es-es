---
description: Más información acerca de cómo extender el seguimiento
title: Extensión del seguimiento
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: e387f49eb4b31ce8dc0b726853ef69d20c8af063
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752371"
---
# <a name="extend-tracing"></a>Extender seguimiento

Este ejemplo muestra cómo extender la característica de seguimiento de Windows Communication Foundation (WCF) escribiendo seguimientos de actividad definidos por el usuario en el código del cliente y del servicio. Escribir seguimientos de actividad definidos por el usuario permite al usuario crear actividades de seguimiento y seguimientos de grupo en unidades lógicas de trabajo. También es posible poner en correlación las actividades a través de las transferencias (dentro del mismo punto de conexión) y propagación (a través de los puntos de conexión). En este ejemplo, el seguimiento se habilita para el cliente y el servicio. Para obtener más información sobre cómo habilitar el seguimiento en los archivos de configuración de cliente y de servicio, vea [seguimiento y registro de mensajes](tracing-and-message-logging.md).  
  
 Este ejemplo se basa en el [Introducción](getting-started-sample.md).  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a>Propagación de seguimiento y de actividad  

 El seguimiento de la actividad definida por el usuario permite al usuario crear sus propias actividades de seguimiento para agrupar los seguimientos en unidades lógicas de trabajo, poner en correlación las actividades a través de las transferencias y la propagación, y reducir el costo de rendimiento del seguimiento de WCF (por ejemplo, el costo de espacio en disco de un archivo de registro).  
  
### <a name="add-custom-sources"></a>Agregar orígenes personalizados  

 Los seguimientos definidos por el usuario pueden añadirse tanto al código de cliente como de servicio. La adición de orígenes de seguimiento al cliente o los archivos de configuración de servicio permite que estos seguimientos personalizados se registren y se muestren en la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md). El código siguiente muestra cómo agregar un origen de seguimiento definido por el usuario denominado `ServerCalculatorTraceSource` al archivo de configuración.  
  
```xml  
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
</system.diagnostics>
....
```  
  
### <a name="correlate-activities"></a>Correlación de actividades  

 Para poner en correlación directamente las actividades con los extremos, el atributo `propagateActivity` debe estar establecido en `true` en el origen de seguimiento `System.ServiceModel`. Además, para propagar los seguimientos sin pasar por las actividades de WCF, el seguimiento de la actividad de ServiceModel debe estar desactivado. Esto puede verse en el siguiente ejemplo de código:  
  
> [!NOTE]
> Desactivar el seguimiento de actividades de ServiceModel no es igual que tener el nivel de seguimiento, indicado por la propiedad `switchValue`, definido en desactivado.  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessen-performance-cost"></a>Reducir el costo de rendimiento  

 Al establecer `ActivityTracing` en desactivado en el origen de seguimiento de `System.ServiceModel`, se genera un archivo de seguimiento que contiene solo seguimientos de actividad definidos por el usuario sin ninguno de los seguimientos de actividad de ServiceModel incluidos. La exclusión de los seguimientos de actividad de ServiceModel da como resultado un archivo de registro mucho más pequeño. Sin embargo, se pierde la oportunidad de correlacionar los seguimientos de procesamiento de WCF.  
  
## <a name="set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de supervisión de AppFabric](/previous-versions/appfabric/ff383407(v=azure.10))
