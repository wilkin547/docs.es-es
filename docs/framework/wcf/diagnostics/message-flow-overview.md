---
title: Información general del flujo de mensajes
ms.date: 03/30/2017
ms.assetid: fb0899e1-84cc-4d90-b45b-dc5a50063943
ms.openlocfilehash: 056737b9d057101568274ab8d24c0c0e2780f93a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="message-flow-overview"></a>Información general del flujo de mensajes
En un sistema distribuido que contiene servicios interconectados es necesario determinar las relaciones causales entre los servicios. Es importante conocer los distintos componentes que formaron parte de un flujo de solicitud para admitir escenarios críticos, como los de supervisión de estado, solución de problemas y análisis de la causa raíz. Para habilitar la correlación de seguimientos entre varios servicios, en .NET Framework 4 agregamos compatibilidad a través de las siguientes características:  
  
-   Seguimiento analítico: característica de seguimiento de alto rendimiento y bajo nivel de detalle que usa el Seguimiento de eventos para Windows (ETW).  
  
-   Modelo de actividad de un extremo a otro para servicios de WCF/WF: esta característica admite la correlación de seguimientos que generan los espacios de nombres <xref:System.ServiceModel> y <xref:System.Workflow.ComponentModel>.  
  
-   Seguimiento de ETW para WF: esta característica utiliza los registros de seguimiento generados por los servicios WF para proporcionar visibilidad del progreso y estado actual del flujo de trabajo.  
  
 Los errores que figuran en un registro de seguimiento se pueden utilizar para encontrar defectos en el código o mensajes con formato incorrecto. La propiedad ActivityId del nodo Correlation en el encabezado del mensaje del evento se puede utilizar para determinar la actividad con errores. Para habilitar el seguimiento del flujo de mensajes por Id. de actividad, vea [configurar el seguimiento de flujo de mensaje](../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md). En este tema se muestra cómo habilitar el seguimiento del flujo de mensajes en el proyecto creado en el tutorial de introducción.  
  
### <a name="to-enable-message-flow-tracing-in-the-getting-started-tutorial"></a>Para habilitar el seguimiento del flujo de mensajes en el tutorial de introducción  
  
1.  Abra el Visor de eventos, haga clic en **iniciar**, **ejecutar**y escriba `eventvwr.exe`.  
  
2.  Si no ha habilitado la traza analítica, expanda **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **servidor de aplicaciones** . Seleccione **vista**, **mostrar analíticos y de depuración registros**. Haga clic en **analítico** y seleccione **Habilitar registro**. Deje el Visor de eventos abierto para que se puedan ver los seguimientos.  
  
3.  Abra el ejemplo creado en el [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md) en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]. Observe que debe ejecutar [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] como administrador para que se pueda crear el servicio. Si tiene la [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ejemplos instalados, puede abrir el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md), que contiene el proyecto completado creado en el tutorial.  
  
4.  Haga clic en el **servicio** de proyecto y seleccione **agregar**, **nuevo elemento**. Seleccione **archivo de configuración de aplicación** y haga clic en **Aceptar**.  
  
5.  Agregue el siguiente código al archivo App.Config creado en el paso anterior.  
  
    ```xml  
    <system.serviceModel>  
      <diagnostics>  
        <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>  
      </diagnostics>  
    </system.serviceModel>  
    ```  
  
6.  Ejecute la aplicación de servidor sin depurar presionando CTRL+F5. Ejecutar el proyecto cliente haciendo clic en el **cliente** proyecto y seleccione **depurar**, **Iniciar nueva instancia**.  
  
7.  Para realizar el seguimiento de los eventos del cliente al servidor, agregue lo siguiente al archivo de configuración de la aplicación en el proyecto Cliente.  
  
    ```xml  
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
  
10. Actualice y examine el **analítico** registro.  Busque un evento con el identificador de evento 220.  Seleccione el evento y haga clic en el **detalles** en el panel de vista previa. Este evento contendrá el identificador de correlación de la actividad de llamada.  
  
    ```xml  
    <Correlation ActivityID="{A066CCF1-8AB3-459B-B62F-F79F957A5036}" />  
    ```  
  
    > [!NOTE]
    >  Todos los eventos con el mismo GUID en ActivityID están relacionados con la misma solicitud. Esto se puede utilizar para poner en correlación los mensajes de un cliente concreto y un servicio concreto. Si el cliente llama a otro servicio, el mismo cliente podría identificarse a través de ActivityID.  
  
11. En algunos casos, ActivityID puede cambiar del GUID original a un nuevo ActivityID. En ese caso, se emite un evento de transferencia. Este identificador de evento es 499 y el evento contendrá los siguientes datos en el encabezado.  
  
    ```xml  
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
    >  El evento de transferencia registra el cambio del ActivityID activo con respecto al GUID especificado como el ActivityID para el GUID especificado como RelatedActivityID. Una vez emitido el evento de transferencia, todos los eventos contendrán el nuevo GUID como ActivityID.
