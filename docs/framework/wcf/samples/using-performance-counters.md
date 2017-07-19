---
title: "Uso de contadores de rendimiento | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
caps.latest.revision: 31
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 31
---
# Uso de contadores de rendimiento
Este ejemplo muestra cómo tener acceso a los contadores de rendimiento de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y cómo crear contadores de rendimiento definidos por el usuario.Este ejemplo se basa en el [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  El procedimiento de configuración y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 En este ejemplo, el cliente llama a los cuatro métodos del servicio `ICalculator`.El cliente continúa haciéndolo hasta que el usuario lo interrumpa.El servicio se mantiene sin cambios.  
  
 Los contadores de rendimiento se habilitan en la sección de diagnóstico del archivo Web.config para el servicio, tal y como se muestra en la configuración del ejemplo siguiente.  
  
```  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 Esta tarea también se puede hacer utilizando la [Herramienta del editor de configuración \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Cuando los contadores de rendimiento se habiliten, se habilitará el conjunto completo de contadores de rendimiento [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para el servicio..NET Framework mantiene automáticamente los datos de rendimiento en tres niveles: `ServiceModelService`, `ServiceModelEndpoint` y `ServiceModelOperation`.Cada uno de estos niveles tiene contadores de rendimiento como "Llamadas", "Llamadas por segundo" y "Llamadas de seguridad no autorizadas".  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado el [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código de la edición .NET de C\# o Visual Basic de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### Para ver los datos de rendimiento  
  
1.  Inicie la herramienta Monitor de rendimiento haciendo clic en **Inicio** y en **Ejecutar**, después escriba `perfmon` y haga clic en **Aceptar** o bien, en el Panel de control, seleccione **Herramientas administrativas** y haga doble clic en **Rendimiento**.  
  
    > [!NOTE]
    >  No puede agregar los contadores hasta que el código de ejemplo se esté ejecutando.  
  
2.  Quite los contadores de rendimiento que aparecen seleccionándolos y presionando la tecla Supr.  
  
3.  Agregue los contadores de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] haciendo clic con el botón secundario del mouse en el panel del gráfico y seleccionando **Agregar contadores**.En el cuadro de diálogo **Agregar contadores**, seleccione **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 o ServiceModelService 3.0.0.0** en el cuadro de lista desplegable del objeto Rendimiento.Seleccione los contadores que desea ver en la lista.  
  
    > [!NOTE]
    >  No hay ningún contador de rendimiento de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para un servicio si no hay ningún servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se ejecute en el equipo.  
  
### Para utilizar el editor de configuración para habilitar los contadores  
  
1.  Abra una instancia de SvcConfigEditor.exe.  
  
2.  En el menú Archivo, haga clic en **Abrir** y, a continuación, haga clic en **Archivo de configuración**.  
  
3.  Vaya a la carpeta de servicio de la aplicación de ejemplo y abra el archivo Web.config.  
  
4.  Haga clic en **Diagnóstico** en el árbol de configuración.  
  
5.  Alterne **Contador de rendimiento** en la ventana **Diagnóstico** para mostrar 'Todos'.  
  
6.  Guarde el archivo de configuración y cierre el editor.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## Vea también  
 [Ejemplos de supervisión de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)