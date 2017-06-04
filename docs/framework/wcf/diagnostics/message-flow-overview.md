---
title: "Informaci&#243;n general del flujo de mensajes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fb0899e1-84cc-4d90-b45b-dc5a50063943
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Informaci&#243;n general del flujo de mensajes
En un sistema distribuido que contiene servicios interconectados es necesario determinar las relaciones causales entre los servicios.  Es importante conocer los distintos componentes que formaron parte de un flujo de solicitud para admitir escenarios críticos, como los de supervisión de estado, solución de problemas y análisis de la causa raíz.  Para habilitar la correlación de seguimientos entre varios servicios, en .NET Framework 4 agregamos compatibilidad a través de las siguientes características:  
  
-   Seguimiento analítico: característica de seguimiento de alto rendimiento y bajo nivel de detalle que usa el Seguimiento de eventos para Windows \(ETW\).  
  
-   Modelo de actividad de un extremo a otro para servicios de WCF\/WF: esta característica admite la correlación de seguimientos que generan los espacios de nombres <xref:System.WorkflowModel> y <xref:System.ServiceModel>.  
  
-   Seguimiento de ETW para WF: esta característica utiliza los registros de seguimiento generados por los servicios WF para proporcionar visibilidad del progreso y estado actual del flujo de trabajo.  
  
 Los errores que figuran en un registro de seguimiento se pueden utilizar para encontrar defectos en el código o mensajes con formato incorrecto.  La propiedad ActivityId del nodo Correlation en el encabezado del mensaje del evento se puede utilizar para determinar la actividad con errores.  Para habilitar el seguimiento del flujo de mensajes a través de identificador de actividad, vea [Configurar la traza de flujo de mensajes](../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md).  En este tema se muestra cómo habilitar el seguimiento del flujo de mensajes en el proyecto creado en el tutorial de introducción.  
  
### Para habilitar el seguimiento del flujo de mensajes en el tutorial de introducción  
  
1.  Abra el Visor de eventos; para ello, haga clic en **Inicio** y en **Ejecutar**, y escriba `eventvwr.exe`.  
  
2.  Si no ha habilitado la traza analítica, expanda **Registros de aplicaciones y servicios**, **Microsoft**, **Windows** y **Servidor de aplicaciones\-Aplicaciones** Seleccione **Ver**, **Mostrar registros analíticos y de depuración**.  Haga clic con el botón secundario en **Analítico** y seleccione **Habilitar registro**.  Deje el Visor de eventos abierto para que se puedan ver los seguimientos.  
  
3.  Abra el ejemplo creado en [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md) en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  Observe que debe ejecutar [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] como administrador para que se pueda crear el servicio.  Si tiene instalados los ejemplos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], puede abrir [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md), que contiene el proyecto completado creado en el tutorial.  
  
4.  Haga clic en el proyecto **Servicio** con el botón secundario, y seleccione **Agregar** y **Nuevo elemento**.  Seleccione **Archivo de configuración de aplicaciones** y haga clic en **Aceptar**.  
  
5.  Agregue el siguiente código al archivo App.Config creado en el paso anterior.  
  
    ```  
    <system.serviceModel>  
      <diagnostics>  
        <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>  
      </diagnostics>  
    </system.serviceModel>  
  
    ```  
  
6.  Ejecute la aplicación de servidor sin depurar presionando CTRL\+F5.  Ejecute el proyecto del cliente; para ello, haga clic con el botón secundario en el proyecto **Cliente** y seleccione **Depuración** e **Iniciar nueva instancia**.  
  
7.  Para realizar el seguimiento de los eventos del cliente al servidor, agregue lo siguiente al archivo de configuración de la aplicación en el proyecto Cliente.  
  
    ```  
    <diagnostics>  
      <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>  
    </diagnostics>  
  
    ```  
  
8.  En Program.cs, en el cliente, agregue la siguiente instrucción Using.  
  
    ```  
    using System.Diagnostics;  
  
    ```  
  
9. En el método Main del archivo program.cs del proyecto de cliente, establezca el GUID de seguimiento para que se propague en el registro de eventos.  
  
    ```  
    Guid guid = Guid.NewGuid();  
    Trace.CorrelationManager.ActivityId = guid;  
  
    ```  
  
10. Actualice y examine el registro **Analítico**.  Busque un evento con el identificador de evento 220.  Seleccione el evento y haga clic en la pestaña **Detalles** en el panel de vista previa.  Este evento contendrá el identificador de correlación de la actividad de llamada.  
  
    ```  
    <Correlation ActivityID="{A066CCF1-8AB3-459B-B62F-F79F957A5036}" />  
    ```  
  
    > [!NOTE]
    >  Todos los eventos con el mismo GUID en ActivityID están relacionados con la misma solicitud.  Esto se puede utilizar para poner en correlación los mensajes de un cliente concreto y un servicio concreto.  Si el cliente llama a otro servicio, el mismo cliente podría identificarse a través de ActivityID.  
  
11. En algunos casos, ActivityID puede cambiar del GUID original a un nuevo ActivityID.  En ese caso, se emite un evento de transferencia.  Este identificador de evento es 499 y el evento contendrá los siguientes datos en el encabezado.  
  
    ```  
    <Event xmlns="http://schemas.microsoft.com/win/2004/08/events/event">  
        <System>  
            <Provider Name="Microsoft-Windows-Application Server-Applications" Guid="{c651f5f6-1c0d-492e-8ae1-b4efd7c9d503}" />   
            <EventID>499</EventID>   
            ...  
            <Correlation ActivityID="{A066CCF1-8AB3-459B-B62F-F79F957A5036}" RelatedActivityID="{85FC0930-9C49-42DA-804B-A7368104BD1B}" />   
            ...  
       </System>  
    </Event>  
    ```  
  
    > [!NOTE]
    >  El evento de transferencia registra el cambio del ActivityID activo con respecto al GUID especificado como el ActivityID para el GUID especificado como RelatedActivityID.  Una vez emitido el evento de transferencia, todos los eventos contendrán el nuevo GUID como ActivityID.