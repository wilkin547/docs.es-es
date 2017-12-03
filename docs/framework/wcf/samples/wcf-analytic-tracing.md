---
title: "Traza analítica de WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c238d4c923b00a6c3387caa9bdafd69b126753c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-analytic-tracing"></a>Traza analítica de WCF
Este ejemplo muestra cómo agregar sus propios eventos de seguimiento en el flujo de seguimientos analíticos que [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] escribe en ETW en [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]. Los seguimientos analíticos pretenden facilitar la visibilidad en los servicios sin que el rendimiento se vea penalizado. En este ejemplo se muestra cómo utilizar las API <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> para escribir eventos que se integran con los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] las API <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>, vea <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.  
  
 Para más información sobre el seguimiento de eventos de Windows, consulte [Improve Debugging and Performance Tuning with ETW](http://go.microsoft.com/fwlink/?LinkId=166488).  
  
## <a name="disposing-eventprovider"></a>Eliminar EventProvider  
 En este ejemplo se usa la clase <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>, que implementa el objeto <xref:System.IDisposable?displayProperty=nameWithType>. Al implementar el seguimiento de un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], es probable que pueda utilizar los recursos de <xref:System.Diagnostics.Eventing.EventProvider> mientras dura el servicio. Por esta razón y para conservar la legibilidad, este ejemplo nunca elimina el objeto <xref:System.Diagnostics.Eventing.EventProvider> ajustado. Si por alguna razón su servicio tiene requisitos diferentes para el seguimiento y debe desechar este recurso, debe modificar este ejemplo de acuerdo con los procedimientos recomendados para desechar recursos no administrados. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]desechar recursos no administrados, vea [implementa un método Dispose](http://go.microsoft.com/fwlink/?LinkId=166436).  
  
## <a name="self-hosting-vs-web-hosting"></a>Autohospedaje y Hospedaje web  
 Para los servicios hospedados en Web, los seguimientos analíticos de WCF proporcionan un campo, denominado "HostReference", que se utiliza para identificar el servicio que está emitiendo los seguimientos. Los seguimientos extensibles de usuario pueden participar en este modelo; este ejemplo muestra los procedimientos recomendados para ello. El formato de un host Web hacer referencia cuando la canalización ' &#124;' carácter aparece realmente en el cuadro cadena puede ser cualquiera de las siguientes acciones:  
  
-   Si la aplicación no está en la raíz.  
  
     \<Nombre del sitio >\<ApplicationVirtualPath > &#124;\< ServiceVirtualPath > &#124; \<ServiceName >  
  
-   Si la aplicación está en la raíz.  
  
     \<Nombre del sitio > &#124; \<ServiceVirtualPath > &#124; \<ServiceName >  
  
 Para los servicios autohospedados, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]de seguimientos analíticos no rellenan el campo "HostReference". La clase `WCFUserEventProvider` de este ejemplo se comporta de forma coherente cuando se utiliza en un servicio autohospedado.  
  
## <a name="custom-event-details"></a>Detalles de eventos personalizados  
 El manifiesto del proveedor de eventos de ETW de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] define tres eventos que están diseñados para ser emitidos por los autores de servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] desde dentro del código del servicio. La siguiente tabla muestra un desglose de los tres eventos:  
  
|Evento|Descripción|Id. de evento|  
|-----------|-----------------|--------------|  
|UserDefinedInformationEventOccurred|Emita este evento cuando ocurra algo en un servicio que no constituya un problema. Por ejemplo, podría emitir un evento después de realizar una llamada a una base de datos correctamente.|301|  
|UserDefinedWarningOccurred|Emita este evento cuando se produzca un problema que pueda provocar un error en el futuro. Por ejemplo, puede emitir un evento de advertencia cuando se produce un error en una llamada a una base de datos pero se pudo recuperar retirándose a un almacén de datos redundante.|302|  
|UserDefinedErrorOccurred|Emita este evento cuando el servicio no se comporte como se preveía. Por ejemplo, podría emitir un evento si se produce un error en una llamada a una base de datos y no pudo recuperar los datos de otro lugar.|303|  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo de solución WCFAnalyticTracingExtensibility.sln.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Para ejecutar la solución, presione CTRL+F5.  
  
     En el explorador Web, haga clic en **Calculator.svc**. El URI del documento WSDL para el servicio debería aparecer en el explorador. Copie ese URI.  
  
4.  Ejecute el cliente de prueba de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (WcfTestClient.exe).  
  
     El [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente de prueba (WcfTestClient.exe) se encuentra en la \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] directorio de instalación > \Common7\IDE\ WcfTestClient.exe (valor predeterminado [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] directorio de instalación es C:\Program Files\Microsoft Visual Studio 10.0).  
  
5.  En el [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente de prueba, agregue el servicio seleccionando **archivo**y, a continuación, **Agregar servicio**.  
  
     Agregue la dirección del punto de conexión en el cuadro de entrada.  
  
6.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
     El servicio ICalculator se agrega en el panel izquierdo bajo **Mis proyectos de servicios**.  
  
7.  Abra la aplicación Visor de eventos.  
  
     Antes de invocar el servicio, inicie el Visor de eventos y asegúrese de que el registro de eventos escucha los eventos de seguimiento emitidos por el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
8.  Desde el **iniciar** menú, seleccione **herramientas administrativas**y, a continuación, **Visor de eventos**. Habilitar la **analítico** y **depurar** registros.  
  
9. En la vista de árbol en el Visor de eventos, navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Servidor de aplicaciones**. Haga clic en **servidor de aplicaciones**, seleccione **vista**y, a continuación, **mostrar registros analíticos y depuración**.  
  
     Asegúrese de que el **mostrar registros analíticos y depuración** opción está activada. Habilitar la **analítico** registro.  
  
     En la vista de árbol en el Visor de eventos, navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**,  **Servidor de aplicaciones**y, a continuación, **analíticos**. Haga clic en **analítico** y seleccione **Habilitar registro**.  
  
10. Pruebe el servicio con el Cliente de prueba WCF.  
  
    1.  En el cliente de prueba WCF, haga doble clic en **Add()** bajo el nodo de servicio ICalculator.  
  
         El **Add()** método aparece en el panel derecho con dos parámetros.  
  
    2.  Escriba 2 en el primer parámetro y 3 en el segundo.  
  
    3.  Haga clic en **Invoke** para invocar el método.  
  
11. Vaya a la **Visor de eventos** ventana que ya tiene abierta. Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **aplicación Aplicaciones de servidor**.  
  
12. Haga clic en el **analítico** nodo y seleccione **actualizar**.  
  
     Los eventos aparecen en el panel derecho.  
  
13. Busque el evento con el identificador 303 y haga doble clic en él para abrirlo e inspeccionar su contenido.  
  
     Este evento fue emitido por el `Add()` método del servicio ICalculator y tenía una carga igual a "2 + 3 = 5".  
  
#### <a name="to-clean-up-optional"></a>Para realizar la limpieza (Opcional)  
  
1.  Abra **Visor de eventos**.  
  
2.  Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación,  **Aplicaciones de servidor**. Haga clic en **analítico** y seleccione **Deshabilitar registro**.  
  
3.  Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**,  **Aplicaciones de servidor**y, a continuación, **analíticos**. Haga clic en **analítico** y seleccione **Vaciar registro**.  
  
4.  Haga clic en **borrar** para borrar los eventos.  
  
## <a name="known-issue"></a>Problema conocido  
 Hay un problema conocido en la **Visor de eventos** donde no puede descodificar eventos de ETW. Puede recibir un mensaje de error que dice: "la descripción del Id. de evento \<id > de origen no se puede encontrar aplicaciones de servidor de aplicación de Microsoft Windows. El componente que genera este evento no está instalado en el equipo local, o bien la instalación está dañada. Puede instalar o reparar el componente en el equipo local." Si se produce este error, seleccione **actualizar** desde el **acciones** menú. El evento debería descodificarse entonces correctamente.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de supervisión de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
