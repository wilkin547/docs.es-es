---
title: Traza analítica de WCF
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: ef636a672d9384e8e3d658f0488cfaadb8d293e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183219"
---
# <a name="wcf-analytic-tracing"></a>Traza analítica de WCF
En este ejemplo se muestra cómo agregar sus propios eventos de seguimiento en la secuencia de [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]seguimientos analíticos que Windows Communication Foundation (WCF) escribe en ETW en . Los seguimientos analíticos pretenden facilitar la visibilidad en los servicios sin que el rendimiento se vea penalizado. En este ejemplo se <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> muestra cómo usar las API para escribir eventos que se integran con servicios WCF.  
  
 Para obtener más <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> información acerca <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>de las API, consulte .  
  
 Para obtener más información sobre el seguimiento de eventos en Windows, consulte [Mejorar la depuración y](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw)el ajuste del rendimiento con ETW .  
  
## <a name="disposing-eventprovider"></a>Eliminar EventProvider  
 En este ejemplo se usa la clase <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>, que implementa el objeto <xref:System.IDisposable?displayProperty=nameWithType>. Al implementar el seguimiento de un servicio WCF, <xref:System.Diagnostics.Eventing.EventProvider>es probable que pueda usar los recursos 's durante la duración del servicio. Por esta razón y para conservar la legibilidad, este ejemplo nunca elimina el objeto <xref:System.Diagnostics.Eventing.EventProvider> ajustado. Si por alguna razón su servicio tiene requisitos diferentes para el seguimiento y debe desechar este recurso, debe modificar este ejemplo de acuerdo con los procedimientos recomendados para desechar recursos no administrados. Para obtener más información sobre la eliminación de recursos no administrados, vea [Implementación de un método Dispose](https://docs.microsoft.com/dotnet/standard/garbage-collection/implementing-dispose).  
  
## <a name="self-hosting-vs-web-hosting"></a>Autohospedamiento y hospedamiento en web  
 Para los servicios hospedados en Web, los seguimientos analíticos de WCF proporcionan un campo, denominado "HostReference", que se usa para identificar el servicio que emite los seguimientos. Los seguimientos extensibles de usuario pueden participar en este modelo; este ejemplo muestra los procedimientos recomendados para ello. El formato de una referencia de host Web cuando el carácter '&#124;' de la canalización aparece realmente en la cadena resultante puede ser cualquiera de los siguientes:  
  
- Si la aplicación no está en la raíz.  
  
     \<SiteName \<>> \<ApplicationVirtualPath \<>&#124;ServiceVirtualPath>&#124;ServiceName  
  
- Si la aplicación está en la raíz.  
  
     \<SiteName \<>&#124;ServiceVirtualPath>&#124;\<ServiceName>  
  
 Para los servicios autohospedados, los seguimientos analíticos de WCF no rellenan el campo "HostReference". La clase `WCFUserEventProvider` de este ejemplo se comporta de forma coherente cuando se utiliza en un servicio autohospedado.  
  
## <a name="custom-event-details"></a>Detalles de eventos personalizados  
 Manifiesto del proveedor de eventos ETW de WCF define tres eventos que están diseñados para ser emitidos por los autores del servicio WCF desde dentro del código de servicio. La siguiente tabla muestra un desglose de los tres eventos:  
  
|Evento|Descripción|Id. de evento|  
|-----------|-----------------|--------------|  
|UserDefinedInformationEventOccurred|Emita este evento cuando ocurra algo en un servicio que no constituya un problema. Por ejemplo, podría emitir un evento después de realizar una llamada a una base de datos correctamente.|301|  
|UserDefinedWarningOccurred|Emita este evento cuando se produzca un problema que pueda provocar un error en el futuro. Por ejemplo, puede emitir un evento de advertencia cuando se produce un error en una llamada a una base de datos pero se pudo recuperar retirándose a un almacén de datos redundante.|302|  
|UserDefinedErrorOccurred|Emita este evento cuando el servicio no se comporte como se preveía. Por ejemplo, podría emitir un evento si se produce un error en una llamada a una base de datos y no pudo recuperar los datos de otro lugar.|303|  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1. Con Visual Studio 2012, abra el wcfanalyticTracingExtensibility.sln archivo de solución.  
  
2. Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3. Para ejecutar la solución, presione CTRL+F5.  
  
     En el explorador web, haga clic en **Calculator.svc**. El URI del documento WSDL para el servicio debería aparecer en el explorador. Copie ese URI.  
  
4. Ejecute el cliente de prueba WCF (WcfTestClient.exe).  
  
     El cliente de prueba WCF (WcfTestClient.exe) se encuentra en `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`. El dir de instalación predeterminado de `C:\Program Files\Microsoft Visual Studio 10.0`Visual Studio 2012 es .  
  
5. En el cliente de prueba WCF, agregue el servicio seleccionando **Archivo**y, a continuación, **Agregar servicio**.  
  
     Agregue la dirección del punto de conexión en el cuadro de entrada.  
  
6. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
     El servicio ICalculator se agrega en el panel izquierdo en **Mis proyectos**de servicio .  
  
7. Abra la aplicación Visor de eventos.  
  
     Antes de invocar el servicio, inicie el Visor de eventos y asegúrese de que el registro de eventos está escuchando los eventos de seguimiento emitidos desde el servicio WCF.  
  
8. En el menú **Inicio** , seleccione **Herramientas administrativas**y, a continuación, Visor **de eventos**. Habilite los registros **analíticos** y **de depuración.**  
  
9. En la vista de árbol del Visor de eventos, vaya a **Visor de**eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**y, a continuación, Aplicaciones **del servidor**de aplicaciones . Haga clic con el botón secundario en **Application Server-Applications**, seleccione **View**y, a continuación, Mostrar registros **analíticos y de depuración**.  
  
     Asegúrese de que la opción Mostrar registros **analíticos y de depuración** esté marcada. Habilite el registro **analítico.**  
  
     En la vista de árbol del Visor de eventos, vaya a **Visor de**eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**, Aplicaciones del **servidor de**aplicaciones y, a continuación, **Analítico**. Haga clic con el botón derecho en **Analítico** y seleccione **Habilitar registro**.  
  
10. Pruebe el servicio con el Cliente de prueba WCF.  
  
    1. En el cliente de prueba WCF, haga doble clic en **Add()** en el nodo de servicio ICalculator.  
  
         El método **Add()** aparece en el panel derecho con dos parámetros.  
  
    2. Escriba 2 en el primer parámetro y 3 en el segundo.  
  
    3. Haga clic en **Invocar** para invocar el método.  
  
11. Vaya a la ventana **Visor de** eventos que ya ha abierto. Vaya a **Visor de**eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**, **Aplicaciones del servidor de**aplicaciones .  
  
12. Haga clic con el botón derecho en el nodo **Analítico** y seleccione **Actualizar**.  
  
     Los eventos aparecen en el panel derecho.  
  
13. Busque el evento con el identificador 303 y haga doble clic en él para abrirlo e inspeccionar su contenido.  
  
     Este evento fue emitido `Add()` por el método del servicio ICalculator y tiene una carga igual a "2+3-5".  
  
#### <a name="to-clean-up-optional"></a>Para realizar la limpieza (Opcional)  
  
1. Abra **Visor de eventos**.  
  
2. Vaya a **Visor de**eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**y, a continuación, **Aplicaciones de servidor de**aplicaciones . Haga clic con el botón derecho en **Analítico** y seleccione **Desactivar registro**.  
  
3. Vaya a **Visor**de eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**, **Aplicaciones-servidor de**aplicaciones y, a **continuación, Analítico**. Haga clic con el botón derecho en **Analítico** y seleccione **Borrar registro**.  
  
4. Haga clic en **Borrar** para borrar los eventos.  
  
## <a name="known-issue"></a>Problema conocido  
 Hay un problema conocido en el **Visor de** eventos donde puede no descodificar eventos ETW. Es posible que vea un mensaje de error \<que dice: "No se puede encontrar la descripción del identificador de evento> de microsoft-Windows-Application Server-Applications de origen. El componente que provoca este evento no está instalado en el equipo local o la instalación está dañada. Puede instalar o reparar el componente en el equipo local." Si se produce este error, seleccione **Actualizar** en el menú **Acciones.** El evento debería descodificarse entonces correctamente.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a>Consulte también

- [Ejemplos de supervisión de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
