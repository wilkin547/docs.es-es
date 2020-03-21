---
title: Uso de contadores de rendimiento
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 7ffd9f5de5efb4be22968958246839e804daf23d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143582"
---
# <a name="using-performance-counters"></a>Uso de contadores de rendimiento
En este ejemplo se muestra cómo tener acceso a los contadores de rendimiento de Windows Communication Foundation (WCF) y cómo crear contadores de rendimiento definidos por el usuario. Este ejemplo se basa en la [introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 En este ejemplo, el cliente llama a los cuatro métodos del servicio `ICalculator`. El cliente continúa haciéndolo hasta que el usuario lo interrumpa. El servicio se mantiene sin cambios.  
  
 Los contadores de rendimiento se habilitan en la sección de diagnóstico del archivo Web.config para el servicio, tal y como se muestra en la configuración del ejemplo siguiente.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />
  </system.serviceModel>  
</configuration>  
```  
  
 Esta tarea también se puede realizar mediante la herramienta Editor de configuración [(SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Cuando se habilitan los contadores de rendimiento, se habilita todo el conjunto de contadores de rendimiento WCF para el servicio. .NET Framework mantiene automáticamente los datos de rendimiento en tres niveles: `ServiceModelService`, `ServiceModelEndpoint` y `ServiceModelOperation`. Cada uno de estos niveles tiene contadores de rendimiento como "Llamadas", "Llamadas por segundo" y "Llamadas de seguridad no autorizadas".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de un equipo o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .  
  
### <a name="to-view-performance-data"></a>Para ver los datos de rendimiento  
  
1. Inicie la herramienta Monitor de rendimiento haciendo `perfmon` clic en **Inicio**, **Ejecutar...**, escriba y haga clic en **Aceptar,** o en el Panel de control, seleccione **Herramientas administrativas** y haga doble clic en **Rendimiento**.  
  
    > [!NOTE]
    > No puede agregar los contadores hasta que el código de ejemplo se esté ejecutando.  
  
2. Quite los contadores de rendimiento que aparecen seleccionándolos y presionando la tecla Supr.  
  
3. Agregue contadores WCF haciendo clic con el botón derecho en el panel de gráficos y seleccionando **Agregar contadores**. En el cuadro de diálogo **Agregar contadores,** seleccione **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 o ServiceModelService 3.0.0.0** en el cuadro de lista desplegable Objeto de rendimiento. Seleccione los contadores que desea ver en la lista.  
  
    > [!NOTE]
    > No hay contadores de rendimiento WCF para un servicio si no hay servicios WCF que se ejecutan en el equipo.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>Para utilizar el editor de configuración para habilitar los contadores  
  
1. Abra una instancia de SvcConfigEditor.exe.  
  
2. En el menú Archivo, haga clic en **Abrir** y, a continuación, haga clic en **Archivo de configuración...**.  
  
3. Vaya a la carpeta de servicio de la aplicación de ejemplo y abra el archivo Web.config.  
  
4. Haga clic en **Diagnóstico** en el árbol Configuración.  
  
5. Alternar **contador de rendimiento** en la ventana **Diagnóstico** para mostrar 'Todos'.  
  
6. Guarde el archivo de configuración y cierre el editor.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>Consulte también

- [Ejemplos de supervisión de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
