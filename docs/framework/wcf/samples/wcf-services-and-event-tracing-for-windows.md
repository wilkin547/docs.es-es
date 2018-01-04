---
title: Servicios de WCF y seguimiento de eventos para Windows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cb8924cc04442e3b9eda5e251e6dcdc57f5660c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-services-and-event-tracing-for-windows"></a>Servicios de WCF y seguimiento de eventos para Windows
Este ejemplo muestra cómo utilizar la traza analítica en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para emitir eventos en Seguimiento de eventos para Windows (ETW). Los seguimientos analíticos son los eventos emitidos en los puntos clave de la pila de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que permiten solucionar problemas de los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en un entorno de producción.  
  
 El seguimiento analítico de servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede activar en un entorno de producción con una repercusión mínima en el rendimiento. Estos seguimientos se emiten como eventos para una sesión de ETW.  
  
 En este ejemplo se incluye un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] básico en el que los eventos se emiten desde l servicio al registro de eventos, que se puede ver con el Visor de eventos. También es posible iniciar una sesión de ETW dedicada que realice escuchas para los eventos del servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. En el ejemplo se incluye un script para crear una sesión de ETW dedicada que almacena los eventos en un archivo binario que se puede leer utilizando el Visor de eventos.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo de solución EtwAnalyticTraceSample.sln.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Para ejecutar la solución, presione CTRL+F5.  
  
     En el explorador Web, haga clic en **Calculator.svc**. El URI del documento WSDL para el servicio debería aparecer en el explorador. Copie ese URI.  
  
     De forma predeterminada, el servicio empieza a realizar escuchas para las solicitudes en el puerto 1378 (http://localhost:1378/Calculator.svc).  
  
4.  Ejecute el cliente de prueba de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (WcfTestClient.exe).  
  
     El [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente de prueba (WcfTestClient.exe) se encuentra en la \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] directorio de instalación > \Common7\IDE\ WcfTestClient.exe (valor predeterminado [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] directorio de instalación es C:\Program Files\Microsoft Visual Studio 10.0).  
  
5.  En el [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente de prueba, agregue el servicio seleccionando **archivo**y, a continuación, **Agregar servicio**.  
  
     Agregue la dirección del punto de conexión en el cuadro de entrada. El valor predeterminado es http://localhost:1378/Calculator.svc.  
  
6.  Abra la aplicación Visor de eventos.  
  
     Antes de invocar el servicio, inicie el Visor de eventos y asegúrese de que el registro de eventos escucha los eventos de seguimiento emitidos por el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
7.  Desde el **iniciar** menú, seleccione **herramientas administrativas**y, a continuación, **Visor de eventos**.  Habilitar la **analítico** y **depurar** registros.  
  
8.  En la vista de árbol en el Visor de eventos, navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Servidor de aplicaciones**. Haga clic en **servidor de aplicaciones**, seleccione **vista**y, a continuación, **mostrar registros analíticos y depuración**.  
  
     Asegúrese de que el **mostrar registros analíticos y depuración** opción está activada.  
  
9. Habilitar la **analítico** registro.  
  
     En la vista de árbol en el Visor de eventos, navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Servidor de aplicaciones**. Haga clic en **analítico** y seleccione **Habilitar registro**.  
  
#### <a name="to-test-the-service"></a>Para probar el servicio  
  
1.  Cambie de nuevo al cliente de prueba de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], haga doble clic en `Divide` y mantenga los valores predeterminados, que especifican el denominador 0.  
  
     Si el denominador es 0, el servicio produce un error.  
  
2.  Observe los eventos emitidos desde el servicio.  
  
     Cambie al Visor de eventos y navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Servidor de aplicaciones**. Haga clic en **analítico** y seleccione **actualizar**.  
  
     Los eventos de seguimiento analítico de WCF se muestran en el visor de eventos. Observe que dado que el servicio inició un error, se muestra un evento de seguimiento del error en el visor de eventos.  
  
3.  Repita los pasos 1 y 2, pero con entradas válidas. El valor del parámetro `N2` puede ser cualquier número distinto de 0.  
  
     Actualice el canal analítico para ver los eventos de WCF que no incluyen ningún evento de error.  
  
 En el ejemplo se muestran los eventos de seguimiento analíticos emitidos desde un servicio WCF.  
  
#### <a name="to-cleanup-optional"></a>Para realizar la limpieza (Opcional)  
  
1.  Abra el Visor de eventos.  
  
2.  Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación,  **Aplicaciones de servidor**. Haga clic en **analítico** y seleccione **Deshabilitar registro**.  
  
3.  Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación,  **Aplicaciones de servidor**. Haga clic en **analítico** y seleccione **Vaciar registro**.  
  
4.  Elija la **borrar** opción para borrar los eventos.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de supervisión de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
