---
title: "Traza anal&#237;tica de WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Traza anal&#237;tica de WCF
Este ejemplo muestra cómo agregar sus propios eventos de seguimiento en el flujo de seguimientos analíticos que [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] escribe en ETW en [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].Los seguimientos analíticos pretenden facilitar la visibilidad en los servicios sin que el rendimiento se vea penalizado.En este ejemplo se muestra cómo utilizar las API <xref:System.Diagnostics.Eventing?displayProperty=fullName> para escribir eventos que se integran con los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] las API <xref:System.Diagnostics.Eventing?displayProperty=fullName>, vea <xref:System.Diagnostics.Eventing?displayProperty=fullName>.  
  
 Para obtener más información acerca de la traza de eventos en Windows, vea [Mejorar el ajuste de la depuración y el rendimiento con ETW](http://go.microsoft.com/fwlink/?LinkId=166488).  
  
## Eliminar EventProvider  
 En este ejemplo se usa la clase <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=fullName>, que implementa el objeto <xref:System.IDisposable?displayProperty=fullName>.Al implementar el seguimiento de un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], es probable que pueda utilizar los recursos de <xref:System.Diagnostics.Eventing.EventProvider> mientras dura el servicio.Por esta razón y para conservar la legibilidad, este ejemplo nunca elimina el objeto <xref:System.Diagnostics.Eventing.EventProvider> ajustado.Si por alguna razón su servicio tiene requisitos diferentes para el seguimiento y debe desechar este recurso, debe modificar este ejemplo de acuerdo con los procedimientos recomendados para desechar recursos no administrados.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo desechar recursos no administrados, vea [Implementar un método Dispose](http://go.microsoft.com/fwlink/?LinkId=166436).  
  
## Autohospedaje yHospedaje web  
 Para los servicios hospedados en web, los seguimientos analíticos de WCF proporcionan un campo, denominado "HostReference", que se utiliza para identificar el servicio que está emitiendo los seguimientos.Los seguimientos extensibles de usuario pueden participar en este modelo; este ejemplo muestra los procedimientos recomendados para ello.El formato de una referencia al hospedamiento en web cuando el carácter '&#124;' de canalización aparece realmente en la cadena resultante puede ser cualquiera de los siguientes:  
  
-   Si la aplicación no está en la raíz.  
  
     \<nombreDeSitio\>\<rutaDeAccesoVirtualDeAplicación\>&#124;\<rutaDeAccesoVirtualDeServicio\>&#124;\<nombreDeServicio\>  
  
-   Si la aplicación está en la raíz.  
  
     \<nombreDeSitio\>&#124;\<rutaDeAccesoVirtualDeServicio\>&#124;\<nombreDeServicio\>  
  
 En los servicios autohospedados, los seguimientos analíticos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no rellenan el campo "HostReference".La clase `WCFUserEventProvider` de este ejemplo se comporta de forma coherente cuando se utiliza en un servicio autohospedado.  
  
## Detalles de eventos personalizados  
 El manifiesto del proveedor de eventos de ETW de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] define tres eventos que están diseñados para ser emitidos por los autores de servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] desde dentro del código del servicio.La siguiente tabla muestra un desglose de los tres eventos:  
  
|Evento|Descripción|Identificador del evento|  
|------------|-----------------|------------------------------|  
|UserDefinedInformationEventOccurred|Emita este evento cuando ocurra algo en un servicio que no constituya un problema.Por ejemplo, podría emitir un evento después de realizar una llamada a una base de datos correctamente.|301|  
|UserDefinedWarningOccurred|Emita este evento cuando se produzca un problema que pueda provocar un error en el futuro.Por ejemplo, puede emitir un evento de advertencia cuando se produce un error en una llamada a una base de datos pero se pudo recuperar retirándose a un almacén de datos redundante.|302|  
|UserDefinedErrorOccurred|Emita este evento cuando el servicio no se comporte como se preveía.Por ejemplo, podría emitir un evento si se produce un error en una llamada a una base de datos y no pudo recuperar los datos de otro lugar.|303|  
  
#### Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo de solución WCFAnalyticTracingExtensibility.sln.  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Para ejecutar la solución, presione CTRL\+F5.  
  
     En el explorador web, haga clic en **Calculator.svc**.El URI del documento WSDL para el servicio debería aparecer en el explorador.Copie ese URI.  
  
4.  Ejecute el cliente de prueba de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] \(WcfTestClient.exe\).  
  
     El cliente de prueba de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] \(WcfTestClient.exe\) se encuentra en el \<directorio de instalación de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] \>\\Common7\\IDE\\WcfTestClient.exe \(de forma predeterminada, el directorio de instalación de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] es C:\\Common7\\IDE\\ WcfTestClient.exe\).  
  
5.  Dentro del cliente de prueba de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], agregue el servicio seleccionando **Archivo** y, a continuación, **Agregar servicio**.  
  
     Agregue la dirección del extremo en el cuadro de entrada.  
  
6.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
     El servicio ICalculator se agrega en el panel izquierdo bajo **Mis proyectos de servicios**.  
  
7.  Abra la aplicación Visor de eventos.  
  
     Antes de invocar el servicio, inicie el Visor de eventos y asegúrese de que el registro de eventos escucha los eventos de seguimiento emitidos por el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
8.  En el menú **Inicio**, seleccione **Herramientas administrativas** y, a continuación, **Visor de eventos**.Habilite los registros de **Depuración** y **Analíticos**.  
  
9. En la vista de árbol del Visor de eventos, navegue hasta **Visor de eventos**, **Registros de aplicaciones y servicios**, **Microsoft** **Windows** y **Servidor de aplicaciones\-Aplicaciones**.Haga clic con el botón secundario en **Servidor de aplicaciones\-Aplicaciones**, seleccione **Ver** y, después, **Mostrar registros analíticos y de depuración**.  
  
     Asegúrese de que esté activada la opción **Mostrar registros analíticos y de depuración**.Habilite el registro **Analítico**.  
  
     íEn la vista de árbol del Visor de eventos, navegue hasta **Visor de eventos**, **Registros de aplicaciones y servicios**, **Microsoft** **Windows**, **Servidor de aplicaciones\-Aplicaciones** y **Analítico**.Haga clic con el botón secundario en **Analítico** y seleccione **Habilitar registro**.  
  
10. Pruebe el servicio con el cliente de prueba de WCF.  
  
    1.  En el cliente de prueba de WCF, haga doble clic en **Add\(\)** bajo el nodo de servicio ICalculator.  
  
         El método **Add\(\)** aparece en el panel derecho con dos parámetros.  
  
    2.  Escriba 2 en el primer parámetro y 3 en el segundo.  
  
    3.  Haga clic en **Invocar** para invocar el método.  
  
11. Vaya a la ventana del **Visor de eventos** que ya ha abierto.Navegue hasta **Visor de eventos**, **Registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **Aplicaciones de servidor\-Aplicaciones**.  
  
12. Haga clic con el botón secundario en el nodo **Analítico** y seleccione **Actualizar**.  
  
     Los eventos aparecen en el panel derecho.  
  
13. Busque el evento con el identificador 303 y haga doble clic en él para abrirlo e inspeccionar su contenido.  
  
     Este evento fue emitido por el método `Add()` del servicio ICalculator y tenía una carga igual a "2\+3\=5".  
  
#### Para realizar la limpieza \(Opcional\)  
  
1.  Abra el **Visor de eventos**.  
  
2.  Desplácese hasta **Visor de eventos**, **Registros de aplicaciones y servicios**, **Microsoft** **Windows** y **Aplicaciones de servidor\-Aplicaciones**.Haga clic con el botón secundario en **Analítico** y seleccione **Deshabilitar registro**.  
  
3.  Desplácese hasta **Visor de eventos**, **Registros de aplicaciones y servicios**, **Microsoft** **Windows**, **Aplicaciones de servidor\-Aplicaciones** y, después, en **Analítico**.Haga clic con el botón secundario en **Analítico** y seleccione **Borrar registro**.  
  
4.  Haga clic en **Borrar** para borrar los eventos.  
  
## Problema conocido  
 Existe un problema conocido en el **Visor de eventos** en virtud del cual el visor no puede descodificar eventos de ETW.Puede ver un mensaje de error similar a: "No se puede encontrar la descripción del id. de evento \<id.\> del origen Microsoft\-Windows\-Servidor de aplicaciones\-Aplicaciones.El componente que genera este evento no está instalado en el equipo local, o bien la instalación está dañada.Puede instalar o reparar el componente en el equipo local". Si encuentra este error, seleccione **Actualizar** en el menú **Acciones**.El evento debería descodificarse entonces correctamente.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## Vea también  
 [Ejemplos de supervisión de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)