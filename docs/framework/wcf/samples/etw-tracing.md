---
title: Seguimiento ETW
description: Este ejemplo muestra cómo implementar el seguimiento de un extremo a otro (E2E) mediante el seguimiento de eventos para Windows (ETW) y ETWTraceListener.
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: 6e7526ef05d672b550599e3b12a4b083e9130b96
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547146"
---
# <a name="etw-tracing"></a>Seguimiento ETW
Este ejemplo muestra cómo implementar el seguimiento de un extremo a otro (E2E) mediante el Seguimiento de eventos para Windows (ETW) y `ETWTraceListener` que se proporciona este ejemplo. El ejemplo se basa en el [Introducción](getting-started-sample.md) e incluye el seguimiento de ETW.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 En este ejemplo se da por supuesto que está familiarizado con el [seguimiento y el registro de mensajes](tracing-and-message-logging.md).  
  
 Cada origen de seguimiento en el modelo de seguimiento<xref:System.Diagnostics> puede tener varios agentes de escucha de seguimiento que determinan donde y cómo se siguen paso a paso los datos. El tipo de agente de escucha define el formato en el que la información de seguimiento está registrada. El ejemplo de código siguiente muestra cómo agregar el agente de escucha a la configuración.  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel"
             switchValue="Verbose,ActivityTracing"  
             propagateActivity="true">  
            <listeners>  
                <add type=  
                   "System.Diagnostics.DefaultTraceListener"  
                   name="Default">  
                   <filter type="" />  
                </add>  
                <add name="ETW">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
        <add type=  
            "Microsoft.ServiceModel.Samples.EtwTraceListener, ETWTraceListener"  
            name="ETW" traceOutputOptions="Timestamp">  
            <filter type="" />  
       </add>  
    </sharedListeners>  
</system.diagnostics>  
```  
  
 Antes de utilizar este agente de escucha, se debe iniciar una Sesión de seguimiento de ETW. Esta sesión se puede iniciar utilizando Logman.exe o Tracelog.exe. Un archivo SetupETW.bat está incluido con este ejemplo para que pueda preparar la Sesión de seguimiento ETW junto con un archivo CleanupETW.bat para cerrar la sesión y completar el archivo de registro.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema. Para obtener más información acerca de estas herramientas, consulte <https://go.microsoft.com/fwlink/?LinkId=56580>  
  
 Al utilizar ETWTraceListener, los rastros están registrados en archivos .etl binarios. Con el seguimiento ServiceModel activado, todos los rastros generados aparecen en el mismo archivo. Use la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) para ver los archivos de registro. ETL y. svclog. El visor crea una vista de un extremo a otro del sistema que permite hacer el seguimiento un mensaje de su origen a su destino y punto de consumo.  
  
 El Agente de escucha de seguimiento de ETW admite el registro circular. Para habilitar esta característica, vaya a **Inicio**, **Ejecutar** y escriba `cmd` para iniciar una consola de comandos. En el comando siguiente, reemplace el parámetro `<logfilename>` con el nombre de su archivo de registro.  
  
```console  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 Los modificadores `-f` y `-max` son opcionales. Especifican respectivamente el formato circular binario y un tamaño de registro de máximo de 1000MB. El modificador `-p` se utiliza para especificar el proveedor de seguimiento. En nuestro ejemplo, `"{411a0819-c24b-428c-83e2-26b41091702e}"` es el GUID para "Proveedor del Ejemplo de "XML ETW.  
  
 Para iniciar la sesión, escriba el siguiente comando.  
  
```console  
logman start Wcf  
```  
  
 Después de haber terminado de registrarse, puede detener la sesión con el comando siguiente.  
  
```console  
logman stop Wcf  
```  
  
 Este proceso genera registros circulares binarios que se pueden procesar con la herramienta de elección, incluida la [herramienta de visor de seguimiento de servicio (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) o tracerpt.  
  
 También puede revisar el ejemplo de [seguimiento circular](circular-tracing.md) para obtener más información sobre un agente de escucha alternativo para realizar el registro circular.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).  
  
    > [!NOTE]
    > Para utilizar los comandos RegisterProvider.bat, SetupETW.bat y CleanupETW.bat, debe ejecutarlos en una cuenta de administrador local. Si usa Windows Vista o posterior, también debe ejecutar el símbolo del sistema con privilegios elevados. Para ello, haga clic con el botón secundario en el icono símbolo del sistema y, a continuación, haga clic en **Ejecutar como administrador**.  
  
3. Antes de ejecutar el ejemplo, ejecute RegisterProvider.bat en el cliente y servidor. Esto prepara el archivo ETWTracingSampleLog.etl resultante para generar rastros que puedan ser leídos por el visor de seguimiento de servicios. Este archivo se puede buscar en la carpeta C:\logs. Si esta carpeta no existe, se debe crear; de lo contrario, no se generará ningún seguimiento. A continuación, ejecute SetupETW.bat en los equipos servidor y cliente para comenzar la sesión de seguimiento de ETW. El archivo SetupETW.bat se encuentra en la carpeta CS\Client.  
  
4. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
5. Cuando complete el ejemplo, ejecute CleanupETW.bat para completar la creación del archivo ETWTracingSampleLog.etl.  
  
6. Abra el archivo ETWTracingSampleLog.etl desde dentro del Visor de seguimiento de servicios. Le solicitarán que guarde el archivo con formato binario como un archivo .svclog.  
  
7. Abra el archivo .svclog creado recientemente desde el Visor de seguimiento de servicios para ver los seguimientos de ServiceModel y ETW.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de supervisión de AppFabric](/previous-versions/appfabric/ff383407(v=azure.10))
