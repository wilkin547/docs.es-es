---
title: Extensión del seguimiento
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: 02dfcc099883ed1d5e97b4f7b1a1f76d49b27a20
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44081036"
---
# <a name="extending-tracing"></a>Extensión del seguimiento
Este ejemplo muestra cómo extender la característica de seguimiento de Windows Communication Foundation (WCF) mediante la escritura de seguimientos de actividad definido por el usuario en el código de cliente y servicio. Esto permite al usuario crear actividades de seguimiento y seguimientos de grupo en las unidades lógicas de trabajo. También es posible poner en correlación las actividades a través de las transferencias (dentro del mismo punto de conexión) y propagación (a través de los puntos de conexión). En este ejemplo, el seguimiento se habilita para el cliente y el servicio. Para obtener más información acerca de cómo habilitar el seguimiento en los archivos de configuración de cliente y el servicio, consulte [seguimiento y registro de mensajes](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  
  
 En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a>Propagación de seguimiento y de actividad  
 Seguimiento de la actividad definido por el usuario permite al usuario crear sus propias actividades de seguimiento para agrupar seguimientos en unidades lógicas de trabajo, poner en correlación las actividades a través de transferencias y propagación y reducir el costo de rendimiento de seguimiento de WCF (por ejemplo, el espacio en disco de costos un archivo de registro).  
  
### <a name="adding-custom-sources"></a>Adición de orígenes personalizados  
 Los seguimientos definidos por el usuario pueden añadirse tanto al código de cliente como de servicio. Agregar orígenes de seguimiento a los archivos de configuración de cliente o servicio permitir que los seguimientos personalizados se graben y se muestra en el [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). El código siguiente muestra cómo agregar un origen de seguimiento definido por el usuario denominado `ServerCalculatorTraceSource` al archivo de configuración.  
  
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
</system.diagnostics>....  
....  
```  
  
### <a name="correlating-activities"></a>Cómo poner en correlación las actividades  
 Para poner en correlación directamente las actividades con los extremos, el atributo `propagateActivity` debe estar establecido en `true` en el origen de seguimiento `System.ServiceModel`. Además, para propagar los seguimientos sin pasar por las actividades WCF, seguimiento de actividad ServiceModel debe estar desactivado. Esto puede verse en el siguiente ejemplo de código:  
  
> [!NOTE]
>  Desactivar el seguimiento de actividades de ServiceModel no es igual que tener el nivel de seguimiento, indicado por la propiedad `switchValue`, definido en desactivado.  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessening-performance-cost"></a>Disminución del coste de rendimiento  
 Al establecer `ActivityTracing` en desactivado en el origen de seguimiento de `System.ServiceModel`, se genera un archivo de seguimiento que contiene solo seguimientos de actividad definidos por el usuario sin ninguno de los seguimientos de actividad de ServiceModel incluidos. Esto genera un archivo de registro de mucho menor tamaño. Sin embargo, la oportunidad de poner en correlación los seguimientos de procesamiento de WCF se pierde.  
  
##### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de supervisión de AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
