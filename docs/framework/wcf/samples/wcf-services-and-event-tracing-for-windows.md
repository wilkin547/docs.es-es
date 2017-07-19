---
title: "Servicios de WCF y seguimiento de eventos para Windows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Servicios de WCF y seguimiento de eventos para Windows
Este ejemplo muestra cómo utilizar la traza analítica en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para emitir eventos en Seguimiento de eventos para Windows \(ETW\).  Los seguimientos analíticos son los eventos emitidos en los puntos clave de la pila de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que permiten solucionar problemas de los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en un entorno de producción.  
  
 El seguimiento analítico de servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede activar en un entorno de producción con una repercusión mínima en el rendimiento.  Estos seguimientos se emiten como eventos para una sesión de ETW.  
  
 En este ejemplo se incluye un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] básico en el que los eventos se emiten desde l servicio al registro de eventos, que se puede ver con el Visor de eventos.  También es posible iniciar una sesión de ETW dedicada que realice escuchas para los eventos del servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  En el ejemplo se incluye un script para crear una sesión de ETW dedicada que almacena los eventos en un archivo binario que se puede leer utilizando el Visor de eventos.  
  
#### Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo de solución EtwAnalyticTraceSample.sln.  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Para ejecutar la solución, presione CTRL\+F5.  
  
     En el explorador web, haga clic en **Calculator.svc**.  El URI del documento WSDL para el servicio debería aparecer en el explorador.  Copie ese URI.  
  
     De forma predeterminada, el servicio empieza a realizar escuchas para las solicitudes en el puerto 1378 \(http:\/\/localhost:1378\/Calculator.svc\).  
  
4.  Ejecute el cliente de prueba de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] \(WcfTestClient.exe\).  
  
     El cliente de prueba de \(WcfTestClient.exe\) [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se encuentra en el \<directorio de instalación [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]\>\\Common7\\IDE\\ WcfTestClient.exe \(de forma predeterminada el directorio de instalación de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] es C:\\Archivos de programa\\Microsoft Visual Studio 10.0\).  
  
5.  Dentro del cliente de prueba de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], agregue el servicio seleccionando **Archivo** y, a continuación, **Agregar servicio**.  
  
     Agregue la dirección del extremo en el cuadro de entrada.  El valor predeterminado es http:\/\/localhost:1378\/Calculator.svc.  
  
6.  Abra la aplicación Visor de eventos.  
  
     Antes de invocar el servicio, inicie el Visor de eventos y asegúrese de que el registro de eventos escucha los eventos de seguimiento emitidos por el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
7.  En el menú **Inicio**, seleccione **Herramientas administrativas** y, a continuación, **Visor de eventos**.  Habilite los registros de **Depuración** y **Analíticos**.  
  
8.  En la vista de árbol del Visor de eventos, navegue hasta **Visor de eventos**, **Registros de aplicaciones y servicios**, **Microsoft** **Windows** y **Servidor de aplicaciones\-Aplicaciones**.  Haga clic con el botón secundario en **Servidor de aplicaciones\-Aplicaciones**, seleccione **Ver** y, después, **Mostrar registros analíticos y de depuración**.  
  
     Asegúrese de que esté activada la opción **Mostrar registros analíticos y de depuración**.  
  
9. Habilite el registro **Analítico**.  
  
     En la vista de árbol del Visor de eventos, navegue hasta **Visor de eventos**, **Registros de aplicaciones y servicios**, **Microsoft** **Windows** y **Servidor de aplicaciones\-Aplicaciones**.  Haga clic con el botón secundario en **Analítico** y seleccione **Habilitar registro**.  
  
#### Para probar el servicio  
  
1.  Cambie de nuevo al cliente de prueba de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], haga doble clic en `Divide` y mantenga los valores predeterminados, que especifican el denominador 0.  
  
     Si el denominador es 0, el servicio produce un error.  
  
2.  Observe los eventos emitidos desde el servicio.  
  
     Cambie al Visor de eventos y navegue hasta **Visor de eventos**, **Registros de aplicaciones y servicios**, **Microsoft**, **Windows** y, después, **Aplicaciones de servidor\-Aplicaciones**.  Haga clic con el botón secundario en **Analítico** y seleccione **Actualizar**.  
  
     Los eventos de seguimiento analítico de WCF se muestran en el visor de eventos.  Observe que dado que el servicio inició un error, se muestra un evento de seguimiento del error en el visor de eventos.  
  
3.  Repita los pasos 1 y 2, pero con entradas válidas.  El valor del parámetro `N2` puede ser cualquier número distinto de 0.  
  
     Actualice el canal analítico para ver los eventos de WCF que no incluyen ningún evento de error.  
  
 En el ejemplo se muestran los eventos de seguimiento analíticos emitidos desde un servicio WCF.  
  
#### Para realizar la limpieza \(Opcional\)  
  
1.  Abra el Visor de eventos.  
  
2.  Desplácese hasta **Visor de eventos**, **Registros de aplicaciones y servicios**, **Microsoft** **Windows** y **Aplicaciones de servidor\-Aplicaciones**.  Haga clic con el botón secundario en **Analítico** y seleccione **Deshabilitar registro**.  
  
3.  Desplácese hasta **Visor de eventos**, **Registros de aplicaciones y servicios**, **Microsoft** **Windows** y **Aplicaciones de servidor\-Aplicaciones**.  Haga clic con el botón secundario en **Analítico** y seleccione **Borrar registro**.  
  
4.  Elija la opción **Borrar** para borrar los eventos.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## Vea también  
 [Ejemplos de supervisión de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)