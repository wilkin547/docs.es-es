---
title: Uso de contadores de rendimiento
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 787a3d08b463980721fb207d029057e14618db5e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44214204"
---
# <a name="using-performance-counters"></a>Uso de contadores de rendimiento
Este ejemplo muestra cómo obtener acceso a los contadores de rendimiento de Windows Communication Foundation (WCF) y cómo crear contadores de rendimiento definido por el usuario. En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 En este ejemplo, el cliente llama a los cuatro métodos del servicio `ICalculator`. El cliente continúa haciéndolo hasta que el usuario lo interrumpa. El servicio se mantiene sin cambios.  
  
 Los contadores de rendimiento se habilitan en la sección de diagnóstico del archivo Web.config para el servicio, tal y como se muestra en la configuración del ejemplo siguiente.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 Esta tarea también puede realizarse mediante la [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Cuando se habilitan los contadores de rendimiento, todo el conjunto de contadores de rendimiento de WCF está habilitado para el servicio. .NET Framework mantiene automáticamente los datos de rendimiento en tres niveles: `ServiceModelService`, `ServiceModelEndpoint` y `ServiceModelOperation`. Cada uno de estos niveles tiene contadores de rendimiento como "Llamadas", "Llamadas por segundo" y "Llamadas de seguridad no autorizadas".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-view-performance-data"></a>Para ver los datos de rendimiento  
  
1.  Inicie la herramienta Monitor de rendimiento haciendo **iniciar**, **ejecutar...** , escriba `perfmon` y haga clic en **Aceptar,** o en el Panel de Control, seleccione **herramientas administrativas** y haga doble clic en **rendimiento**.  
  
    > [!NOTE]
    >  No puede agregar los contadores hasta que el código de ejemplo se esté ejecutando.  
  
2.  Quite los contadores de rendimiento que aparecen seleccionándolos y presionando la tecla Supr.  
  
3.  Agregar contadores WCF haciendo clic en el panel del gráfico y seleccione **agregar contadores**. En el **agregar contadores** cuadro de diálogo, seleccione **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 o ServiceModelService 3.0.0.0** en el objeto de rendimiento, coloque el cuadro de lista desplegable. Seleccione los contadores que desea ver en la lista.  
  
    > [!NOTE]
    >  No hay ningún contador de rendimiento de WCF para un servicio si no hay servicios WCF que se ejecutan en el equipo.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>Para utilizar el editor de configuración para habilitar los contadores  
  
1.  Abra una instancia de SvcConfigEditor.exe.  
  
2.  En el menú archivo, haga clic en **abierto** y, a continuación, haga clic en **archivo de configuración...** .  
  
3.  Vaya a la carpeta de servicio de la aplicación de ejemplo y abra el archivo Web.config.  
  
4.  Haga clic en **diagnósticos** en el árbol de configuración.  
  
5.  Alternar **contador de rendimiento** en el **diagnósticos** ventana para mostrar 'Todos'.  
  
6.  Guarde el archivo de configuración y cierre el editor.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de supervisión de AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
