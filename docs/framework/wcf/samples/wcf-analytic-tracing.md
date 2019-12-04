---
title: Traza analítica de WCF
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: 52a6787f6c7d309b1ae3a932780e4dbcb2ec0792
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715302"
---
# <a name="wcf-analytic-tracing"></a>Traza analítica de WCF
En este ejemplo se muestra cómo agregar sus propios eventos de seguimiento en la secuencia de seguimientos analíticos que Windows Communication Foundation (WCF) escribe en ETW en [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]. Los seguimientos analíticos pretenden facilitar la visibilidad en los servicios sin que el rendimiento se vea penalizado. En este ejemplo se muestra cómo usar las API de <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> para escribir eventos que se integran con los servicios WCF.  
  
 Para obtener más información sobre las API de <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>, vea <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.  
  
 Para obtener más información sobre el seguimiento de eventos en Windows, vea [mejorar la depuración y el ajuste del rendimiento con ETW](https://go.microsoft.com/fwlink/?LinkId=166488).  
  
## <a name="disposing-eventprovider"></a>Eliminar EventProvider  
 En este ejemplo se usa la clase <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>, que implementa el objeto <xref:System.IDisposable?displayProperty=nameWithType>. Al implementar el seguimiento de un servicio WCF, es probable que pueda usar los recursos del <xref:System.Diagnostics.Eventing.EventProvider>para la duración del servicio. Por esta razón y para conservar la legibilidad, este ejemplo nunca elimina el objeto <xref:System.Diagnostics.Eventing.EventProvider> ajustado. Si por alguna razón su servicio tiene requisitos diferentes para el seguimiento y debe desechar este recurso, debe modificar este ejemplo de acuerdo con los procedimientos recomendados para desechar recursos no administrados. Para obtener más información sobre cómo desechar recursos no administrados, vea [implementar un método Dispose](https://go.microsoft.com/fwlink/?LinkId=166436).  
  
## <a name="self-hosting-vs-web-hosting"></a>Autohospedamiento y hospedamiento en web  
 En el caso de los servicios hospedados en Web, los seguimientos analíticos de WCF proporcionan un campo, denominado "HostReference", que se usa para identificar el servicio que emite los seguimientos. Los seguimientos extensibles de usuario pueden participar en este modelo; este ejemplo muestra los procedimientos recomendados para ello. El formato de una referencia de host Web cuando el carácter&#124;' ' de la canalización aparece realmente en la cadena resultante puede ser cualquiera de los siguientes:  
  
- Si la aplicación no está en la raíz.  
  
     \<SiteName >\<ApplicationVirtualPath >&#124;\<ServiceVirtualPath >&#124;\<ServiceName >  
  
- Si la aplicación está en la raíz.  
  
     \<SiteName >&#124;\<ServiceVirtualPath >&#124;\<ServiceName >  
  
 En el caso de los servicios autohospedados, los seguimientos analíticos de WCF no rellenan el campo "HostReference". La clase `WCFUserEventProvider` de este ejemplo se comporta de forma coherente cuando se utiliza en un servicio autohospedado.  
  
## <a name="custom-event-details"></a>Detalles de eventos personalizados  
 El manifiesto de proveedor de eventos ETW de WCF define tres eventos que están diseñados para ser emitidos por los autores de servicios WCF desde el código de servicio. La siguiente tabla muestra un desglose de los tres eventos:  
  
|Event|Descripción|Id. de evento|  
|-----------|-----------------|--------------|  
|UserDefinedInformationEventOccurred|Emita este evento cuando ocurra algo en un servicio que no constituya un problema. Por ejemplo, podría emitir un evento después de realizar una llamada a una base de datos correctamente.|301|  
|UserDefinedWarningOccurred|Emita este evento cuando se produzca un problema que pueda provocar un error en el futuro. Por ejemplo, puede emitir un evento de advertencia cuando se produce un error en una llamada a una base de datos pero se pudo recuperar retirándose a un almacén de datos redundante.|302|  
|UserDefinedErrorOccurred|Emita este evento cuando el servicio no se comporte como se preveía. Por ejemplo, podría emitir un evento si se produce un error en una llamada a una base de datos y no pudo recuperar los datos de otro lugar.|303|  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1. Con Visual Studio 2012, abra el archivo de solución WCFAnalyticTracingExtensibility. sln.  
  
2. Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3. Para ejecutar la solución, presione CTRL+F5.  
  
     En el explorador Web, haga clic en **Calculator. SVC**. El URI del documento WSDL para el servicio debería aparecer en el explorador. Copie ese URI.  
  
4. Ejecute el cliente de prueba de WCF (WcfTestClient. exe).  
  
     El cliente de prueba de WCF (WcfTestClient. exe) se encuentra en `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`. El directorio de instalación predeterminado de Visual Studio 2012 es `C:\Program Files\Microsoft Visual Studio 10.0`.  
  
5. En el cliente de prueba de WCF, agregue el servicio seleccionando **archivo**y, a continuación, **Agregar servicio**.  
  
     Agregue la dirección del punto de conexión en el cuadro de entrada.  
  
6. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
     El servicio ICalculator se agrega en el panel izquierdo en **mis proyectos de servicio**.  
  
7. Abra la aplicación Visor de eventos.  
  
     Antes de invocar el servicio, inicie Visor de eventos y asegúrese de que el registro de eventos está escuchando los eventos de seguimiento emitidos por el servicio WCF.  
  
8. En el menú **Inicio** , seleccione **herramientas administrativas**y, a continuación, **visor de eventos**. Habilitar los registros **analíticos** y de **depuración** .  
  
9. En la vista de árbol de Visor de eventos, vaya a **visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **aplicaciones de servidor de**aplicaciones. Haga clic con el botón derecho en **servidor de aplicaciones-aplicaciones**, seleccione **Ver**y, a continuación, **muestre los registros analíticos y de depuración**.  
  
     Asegúrese de que la opción **Mostrar registros analíticos y de depuración** está activada. Habilitación del registro **analítico** .  
  
     En la vista de árbol de Visor de eventos, vaya a **visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **servidor de aplicaciones-aplicaciones**y, a continuación, **análisis**. Haga clic con el botón secundario en **analítico** y seleccione **Habilitar registro**.  
  
10. Pruebe el servicio con el Cliente de prueba WCF.  
  
    1. En el cliente de prueba WCF, haga doble clic en **Add ()** en el nodo de servicio ICalculator.  
  
         El método **Add ()** aparece en el panel derecho con dos parámetros.  
  
    2. Escriba 2 en el primer parámetro y 3 en el segundo.  
  
    3. Haga clic en **invocar** para invocar el método.  
  
11. Vaya a la ventana de **visor de eventos** que ya ha abierto. Vaya a **visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **servidor de aplicaciones-aplicaciones**.  
  
12. Haga clic con el botón secundario en el nodo **analítico** y seleccione **Actualizar**.  
  
     Los eventos aparecen en el panel derecho.  
  
13. Busque el evento con el identificador 303 y haga doble clic en él para abrirlo e inspeccionar su contenido.  
  
     Este evento fue emitido por el método `Add()` del servicio ICalculator y tiene una carga igual a "2 + 3 = 5".  
  
#### <a name="to-clean-up-optional"></a>Para realizar la limpieza (Opcional)  
  
1. Abra **visor de eventos**.  
  
2. Vaya a **visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **aplicaciones de servidor de**aplicaciones. Haga clic con el botón secundario en **analítico** y seleccione **deshabilitar registro**.  
  
3. Vaya a **visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **aplicaciones de servidor de**aplicaciones y, a continuación, **análisis**. Haga clic con el botón secundario en **analítico** y seleccione **Borrar registro**.  
  
4. Haga clic en **Borrar** para borrar los eventos.  
  
## <a name="known-issue"></a>Problema conocido  
 Existe un problema conocido en el **visor de eventos** en el que se puede producir un error al descodificar los eventos ETW. Es posible que vea un mensaje de error que indica: "no se encuentra la descripción del ID. de evento \<ID > desde el origen Microsoft-Windows-servidor de aplicaciones-aplicaciones. El componente que genera este evento no está instalado en el equipo local, o bien la instalación está dañada. Puede instalar o reparar el componente en el equipo local ". Si se produce este error, seleccione **Actualizar** en el menú **acciones** . El evento debería descodificarse entonces correctamente.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de supervisión de AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
