---
title: Traza analítica de WCF
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: 9ed89bdbe2469a96f2a959c9fda8442e80b6f7ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723360"
---
# <a name="wcf-analytic-tracing"></a>Traza analítica de WCF
Este ejemplo muestra cómo agregar sus propios eventos de seguimiento en la secuencia de los seguimientos analíticos que Windows Communication Foundation (WCF) se escribe en ETW en [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]. Los seguimientos analíticos pretenden facilitar la visibilidad en los servicios sin que el rendimiento se vea penalizado. En este ejemplo se muestra cómo usar el <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> API para escribir los eventos que se integran con los servicios WCF.  
  
 Para obtener más información sobre la <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> API, consulte <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.  
  
 Para obtener más información sobre el seguimiento de eventos en Windows, consulte [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkId=166488).  
  
## <a name="disposing-eventprovider"></a>Eliminar EventProvider  
 En este ejemplo se usa la clase <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>, que implementa el objeto <xref:System.IDisposable?displayProperty=nameWithType>. Al implementar el seguimiento para un servicio WCF, es probable que puede utilizar el <xref:System.Diagnostics.Eventing.EventProvider>de recursos para la duración del servicio. Por esta razón y para conservar la legibilidad, este ejemplo nunca elimina el objeto <xref:System.Diagnostics.Eventing.EventProvider> ajustado. Si por alguna razón su servicio tiene requisitos diferentes para el seguimiento y debe desechar este recurso, debe modificar este ejemplo de acuerdo con los procedimientos recomendados para desechar recursos no administrados. Para obtener más información sobre cómo deshacerse de los recursos no administrados, consulte [implementar un método Dispose](https://go.microsoft.com/fwlink/?LinkId=166436).  
  
## <a name="self-hosting-vs-web-hosting"></a>Autohospedaje y Hospedaje web  
 Para los servicios hospedados en Web, los seguimientos analíticos de WCF proporcionan un campo, denominado "HostReference", que se usa para identificar el servicio que está emitiendo los seguimientos. Los seguimientos extensibles de usuario pueden participar en este modelo; este ejemplo muestra los procedimientos recomendados para ello. El formato de un host Web hacen referencia a cuando la canalización '&#124;' carácter aparece realmente en el cuadro cadena puede ser cualquiera de las siguientes acciones:  
  
- Si la aplicación no está en la raíz.  
  
     \<SiteName>\<ApplicationVirtualPath>&#124;\<ServiceVirtualPath>&#124;\<ServiceName>  
  
- Si la aplicación está en la raíz.  
  
     \<SiteName>&#124;\<ServiceVirtualPath>&#124;\<ServiceName>  
  
 Para los servicios autohospedados, seguimientos analíticos de WCF no rellenan el campo "HostReference". La clase `WCFUserEventProvider` de este ejemplo se comporta de forma coherente cuando se utiliza en un servicio autohospedado.  
  
## <a name="custom-event-details"></a>Detalles de eventos personalizados  
 Manifiesto del proveedor de eventos ETW de WCF define tres eventos que están diseñados para ser emitidos por los autores de servicio WCF desde dentro del código de servicio. La siguiente tabla muestra un desglose de los tres eventos:  
  
|evento|Descripción|Id. de evento|  
|-----------|-----------------|--------------|  
|UserDefinedInformationEventOccurred|Emita este evento cuando ocurra algo en un servicio que no constituya un problema. Por ejemplo, podría emitir un evento después de realizar una llamada a una base de datos correctamente.|301|  
|UserDefinedWarningOccurred|Emita este evento cuando se produzca un problema que pueda provocar un error en el futuro. Por ejemplo, puede emitir un evento de advertencia cuando se produce un error en una llamada a una base de datos pero se pudo recuperar retirándose a un almacén de datos redundante.|302|  
|UserDefinedErrorOccurred|Emita este evento cuando el servicio no se comporte como se preveía. Por ejemplo, podría emitir un evento si se produce un error en una llamada a una base de datos y no pudo recuperar los datos de otro lugar.|303|  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1. Con Visual Studio 2012, abra el archivo de solución WCFAnalyticTracingExtensibility.sln.  
  
2. Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3. Para ejecutar la solución, presione CTRL+F5.  
  
     En el explorador Web, haga clic en **Calculator.svc**. El URI del documento WSDL para el servicio debería aparecer en el explorador. Copie ese URI.  
  
4. Ejecute al cliente de prueba WCF (WcfTestClient.exe).  
  
     El cliente de prueba WCF (WcfTestClient.exe) se encuentra en `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`. El directorio de instalación de Visual Studio 2012 de forma predeterminada es `C:\Program Files\Microsoft Visual Studio 10.0`.  
  
5. En el cliente de prueba WCF, agregue el servicio seleccionando **archivo**y, a continuación, **Agregar servicio**.  
  
     Agregue la dirección del punto de conexión en el cuadro de entrada.  
  
6. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
     El servicio ICalculator se agrega en el panel izquierdo bajo **Mis proyectos de servicios**.  
  
7. Abra la aplicación Visor de eventos.  
  
     Antes de invocar el servicio, inicie el Visor de eventos y asegúrese de que el registro de eventos escucha eventos de seguimiento emitidos desde el servicio WCF.  
  
8. Desde el **iniciar** menú, seleccione **herramientas administrativas**y, a continuación, **Visor de eventos**. Habilitar la **analítico** y **depurar** registros.  
  
9. En la vista de árbol en el Visor de eventos, vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Aplicaciones de servidor-aplicaciones**. Haga clic en **aplicaciones de servidor-aplicaciones**, seleccione **vista**y, a continuación, **mostrar registros analíticos y depuración**.  
  
     Asegúrese de que el **mostrar registros analíticos y depuración** opción está activada. Habilitar la **analítico** registro.  
  
     En la vista de árbol en el Visor de eventos, vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**,  **Servidor de aplicaciones-aplicaciones**y, a continuación, **analíticos**. Haga clic en **analítico** y seleccione **Habilitar registro**.  
  
10. Pruebe el servicio con el Cliente de prueba WCF.  
  
    1. En el cliente de prueba WCF, haga doble clic en **Add()** bajo el nodo de servicio ICalculator.  
  
         El **Add()** método aparece en el panel derecho con dos parámetros.  
  
    2. Escriba 2 en el primer parámetro y 3 en el segundo.  
  
    3. Haga clic en **Invoke** para invocar el método.  
  
11. Vaya a la **Visor de eventos** ventana que ya ha abierto. Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **aplicación Aplicaciones de servidor**.  
  
12. Haga clic en el **analítico** nodo y seleccione **actualizar**.  
  
     Los eventos aparecen en el panel derecho.  
  
13. Busque el evento con el identificador 303 y haga doble clic en él para abrirlo e inspeccionar su contenido.  
  
     Este evento fue emitido por el `Add()` método del servicio ICalculator y tenía una carga igual a "2 + 3 = 5".  
  
#### <a name="to-clean-up-optional"></a>Para realizar la limpieza (Opcional)  
  
1. Abra **Visor de eventos**.  
  
2. Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación,  **Aplicaciones de servidor**. Haga clic en **analítico** y seleccione **Deshabilitar registro**.  
  
3. Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**,  **Servidor de aplicaciones-aplicaciones**y, a continuación, **analíticos**. Haga clic en **analítico** y seleccione **Vaciar registro**.  
  
4. Haga clic en **borrar** para borrar los eventos.  
  
## <a name="known-issue"></a>Problema conocido  
 Hay un problema conocido en el **Visor de eventos** donde no puede descodificar eventos de ETW. Verá un mensaje de error que dice: "La descripción del Id. de evento \<id > de origen no se puede encontrar aplicaciones de servidor de aplicaciones de Microsoft Windows. El componente que genera este evento no está instalado en el equipo local, o bien la instalación está dañada. Puede instalar o reparar el componente en el equipo local." Si se produce este error, seleccione **actualizar** desde el **acciones** menú. El evento debería descodificarse entonces correctamente.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de supervisión de AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
