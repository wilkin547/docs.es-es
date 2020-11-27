---
title: Uso de contadores de rendimiento
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: d3e6b9805bd0b9c5eea991fce4dde2035f8f5c1b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294916"
---
# <a name="using-performance-counters"></a>Uso de contadores de rendimiento

Este ejemplo muestra cómo obtener acceso a los contadores de rendimiento de Windows Communication Foundation (WCF) y cómo crear contadores de rendimiento definidos por el usuario. Este ejemplo se basa en el [Introducción](getting-started-sample.md).  
  
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
  
 Esta tarea también puede realizarse mediante la [herramienta editor de configuración (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Cuando se habilitan los contadores de rendimiento, se habilita el conjunto completo de contadores de rendimiento de WCF para el servicio. .NET Framework mantiene automáticamente los datos de rendimiento en tres niveles: `ServiceModelService`, `ServiceModelEndpoint` y `ServiceModelOperation`. Cada uno de estos niveles tiene contadores de rendimiento como "Llamadas", "Llamadas por segundo" y "Llamadas de seguridad no autorizadas".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
### <a name="to-view-performance-data"></a>Para ver los datos de rendimiento  
  
1. Para iniciar la herramienta Monitor de rendimiento, haga clic en **Inicio**, **Ejecutar.**.., escriba `perfmon` y haga clic en **Aceptar,** o bien, en el panel de control, seleccione **herramientas administrativas** y haga doble clic en **rendimiento**.  
  
    > [!NOTE]
    > No puede agregar los contadores hasta que el código de ejemplo se esté ejecutando.  
  
2. Quite los contadores de rendimiento que aparecen seleccionándolos y presionando la tecla Supr.  
  
3. Agregue los contadores de WCF; para ello, haga clic con el botón secundario en el panel del gráfico y seleccione **Agregar contadores**. En el cuadro de diálogo **Agregar contadores** , seleccione **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 o ServiceModelService 3.0.0.0** en el cuadro de lista desplegable objeto de rendimiento. Seleccione los contadores que desea ver en la lista.  
  
    > [!NOTE]
    > No hay ningún contador de rendimiento de WCF para un servicio si no hay servicios WCF en ejecución en el equipo.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>Para utilizar el editor de configuración para habilitar los contadores  
  
1. Abra una instancia de SvcConfigEditor.exe.  
  
2. En el menú Archivo, haga clic en **abrir** y, a continuación, haga clic en **archivo de configuración.**  
  
3. Vaya a la carpeta de servicio de la aplicación de ejemplo y abra el archivo Web.config.  
  
4. Haga clic en **diagnósticos** en el árbol de configuración.  
  
5. Alterne el **contador de rendimiento** en la ventana **diagnóstico** para mostrar "todos".  
  
6. Guarde el archivo de configuración y cierre el editor.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de supervisión de AppFabric](/previous-versions/appfabric/ff383407(v=azure.10))
