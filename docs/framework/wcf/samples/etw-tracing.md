---
title: "Seguimiento ETW | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
caps.latest.revision: 42
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 42
---
# Seguimiento ETW
Este ejemplo muestra cómo implementar el seguimiento de un extremo a otro \(E2E\) mediante el Seguimiento de eventos para Windows \(ETW\) y `ETWTraceListener` que se proporciona este ejemplo.El ejemplo está basado en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md) e incluye el seguimiento de ETW.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 En este ejemplo se supone que conoce el [Seguimiento y registro de mensajes](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  
  
 Cada origen de seguimiento en el modelo de seguimiento<xref:System.Diagnostics> puede tener varios agentes de escucha de seguimiento que determinan donde y cómo se siguen paso a paso los datos.El tipo de agente de escucha define el formato en el que la información de seguimiento está registrada.El ejemplo de código siguiente muestra cómo agregar el agente de escucha a la configuración.  
  
```  
  
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
  
 Antes de utilizar este agente de escucha, se debe iniciar una Sesión de seguimiento de ETW.Esta sesión se puede iniciar utilizando Logman.exe o Tracelog.exe.Un archivo SetupETW.bat está incluido con este ejemplo para que pueda preparar la Sesión de seguimiento ETW junto con un archivo CleanupETW.bat para cerrar la sesión y completar el archivo de registro.  
  
> [!NOTE]
>  El procedimiento de configuración y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.Para obtener más información sobre estas herramientas, vea [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=56580](http://go.microsoft.com/fwlink/?LinkId=56580).  
  
 Al utilizar ETWTraceListener, los rastros están registrados en archivos .etl binarios.Con el seguimiento ServiceModel activado, todos los rastros generados aparecen en el mismo archivo.Utilice [Herramienta del visor de seguimiento de servicio \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) para ver los archivos de registro .etl y .svclog.El visor crea una vista de un extremo a otro del sistema que permite hacer el seguimiento un mensaje de su origen a su destino y punto de consumo.  
  
 El Agente de escucha de seguimiento de ETW admite el registro circular.Para habilitar esta característica, vaya a **Iniciar**, **Ejecutar** y escriba `cmd` para iniciar una consola de comando.En el comando siguiente, reemplace el parámetro `<logfilename>` con el nombre de su archivo de registro.  
  
```  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 Los modificadores `-max` y `-f` son opcionales.Especifican respectivamente el formato circular binario y un tamaño de registro de máximo de 1000MB.El modificador `-p` se utiliza para especificar el proveedor de seguimiento.En nuestro ejemplo, `"{411a0819-c24b-428c-83e2-26b41091702e}"` es el GUID para "Proveedor del Ejemplo de "XML ETW.  
  
 Para iniciar la sesión, escriba el siguiente comando.  
  
```  
Logman start Wcf  
  
```  
  
 Cuando termine de registrarse, puede detener la sesión con el comando siguiente.  
  
```  
Logman stop Wcf  
```  
  
 Este proceso genera los registros circulares binarios que puede procesar con su herramienta de opción, incluyendo [Herramienta del visor de seguimiento de servicio \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) o Tracerpt.  
  
 También puede revisar la muestra[Seguimiento circular](../../../../docs/framework/wcf/samples/circular-tracing.md) para obtener más información sobre un agente de escucha alternativo para realizar el registro circular.  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
    > [!NOTE]
    >  Para utilizar los comandos RegisterProvider.bat, SetupETW.bat y CleanupETW.bat, debe ejecutarlos en una cuenta de administrador local.Si está utilizando [!INCLUDE[wv](../../../../includes/wv-md.md)] o posterior, también debe ejecutar el símbolo del sistema con privilegios elevados.Para realizar esta acción, haga clic con el botón secundario en el icono del símbolo del sistema, a continuación, haga clic en **Ejecutar como administrador**.  
  
3.  Antes de ejecutar el ejemplo, ejecute RegisterProvider.bat en el cliente y servidor.Esto prepara el archivo ETWTracingSampleLog.etl resultante para generar rastros que puedan ser leídos por el visor de seguimiento de servicios.Este archivo se puede buscar en la carpeta C:\\logs.Si esta carpeta no existe, se debe crear; de lo contrario, no se generará ningún seguimiento.A continuación, ejecute SetupETW.bat en los equipos servidor y cliente para comenzar la sesión de seguimiento de ETW.El archivo SetupETW.bat se encuentra en la carpeta CS\\Client.  
  
4.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
5.  Cuando complete el ejemplo, ejecute CleanupETW.bat para completar la creación del archivo ETWTracingSampleLog.etl.  
  
6.  Abra el archivo ETWTracingSampleLog.etl desde dentro del Visor de seguimiento de servicios.Le solicitarán que guarde el archivo con formato binario como un archivo .svclog.  
  
7.  Abra el archivo .svclog creado recientemente desde el Visor de seguimiento de servicios para ver los seguimientos de ServiceModel y ETW.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## Vea también  
 [Ejemplos de supervisión de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)