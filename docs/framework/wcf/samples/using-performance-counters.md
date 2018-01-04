---
title: Uso de contadores de rendimiento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ef5a499e6d940e45e0c9aab093b0a1c00bb6cc32
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-performance-counters"></a>Uso de contadores de rendimiento
Este ejemplo muestra cómo tener acceso a los contadores de rendimiento de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y cómo crear contadores de rendimiento definidos por el usuario. En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
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
  
 Esta tarea también puede realizarse mediante la [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Cuando los contadores de rendimiento se habiliten, se habilitará el conjunto completo de contadores de rendimiento [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para el servicio. .NET Framework mantiene automáticamente los datos de rendimiento en tres niveles: `ServiceModelService`, `ServiceModelEndpoint` y `ServiceModelOperation`. Cada uno de estos niveles tiene contadores de rendimiento como "Llamadas", "Llamadas por segundo" y "Llamadas de seguridad no autorizadas".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipo único o varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-view-performance-data"></a>Para ver los datos de rendimiento  
  
1.  Inicie la herramienta de Monitor de rendimiento, haga clic en **iniciar**, **ejecutar...** , escriba `perfmon` y haga clic en **Aceptar,** o en el Panel de Control, seleccione **herramientas administrativas** y haga doble clic en **rendimiento**.  
  
    > [!NOTE]
    >  No puede agregar los contadores hasta que el código de ejemplo se esté ejecutando.  
  
2.  Quite los contadores de rendimiento que aparecen seleccionándolos y presionando la tecla Supr.  
  
3.  Agregar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contadores haciendo clic en el panel del gráfico y seleccione **agregar contadores**. En el **agregar contadores** cuadro de diálogo, seleccione **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 o ServiceModelService 3.0.0.0** en el objeto de rendimiento cuadro de lista desplegable. Seleccione los contadores que desea ver en la lista.  
  
    > [!NOTE]
    >  No hay ningún contador de rendimiento de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para un servicio si no hay ningún servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se ejecute en el equipo.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>Para utilizar el editor de configuración para habilitar los contadores  
  
1.  Abra una instancia de SvcConfigEditor.exe.  
  
2.  En el menú archivo, haga clic en **abiertos** y, a continuación, haga clic en **el archivo de configuración...** .  
  
3.  Vaya a la carpeta de servicio de la aplicación de ejemplo y abra el archivo Web.config.  
  
4.  Haga clic en **diagnósticos** en el árbol de configuración.  
  
5.  Alternar **contador de rendimiento** en el **diagnósticos** ventana para mostrar 'All'.  
  
6.  Guarde el archivo de configuración y cierre el editor.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de supervisión de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
