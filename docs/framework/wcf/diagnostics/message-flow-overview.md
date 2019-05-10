---
title: Información general del flujo de mensajes
ms.date: 03/30/2017
ms.assetid: fb0899e1-84cc-4d90-b45b-dc5a50063943
ms.openlocfilehash: 009dd05ab299b92ee5f5cafd1c2131a2e6eb0132
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650256"
---
# <a name="message-flow-overview"></a>Información general del flujo de mensajes
En un sistema distribuido que contiene servicios interconectados es necesario determinar las relaciones causales entre los servicios. Es importante conocer los distintos componentes que formaron parte de un flujo de solicitud para admitir escenarios críticos, como los de supervisión de estado, solución de problemas y análisis de la causa raíz. Para habilitar la correlación de seguimientos entre varios servicios, en .NET Framework 4 agregamos compatibilidad a través de las siguientes características:

- Traza analítica: Un alto rendimiento y la característica de seguimiento de bajo nivel de detalle con el seguimiento de eventos para Windows (ETW).

- Modelo de actividad de extremo a otro para los servicios WCF/WF: Esta característica admite la correlación de seguimientos generados mediante la <xref:System.ServiceModel> y <xref:System.Workflow.ComponentModel> espacios de nombres.

- Seguimiento de ETW para WF: Esta característica utiliza los registros de seguimiento generados por los servicios WF para proporcionar visibilidad sobre el progreso y el estado actual del flujo de trabajo.

 Los errores que figuran en un registro de seguimiento se pueden utilizar para encontrar defectos en el código o mensajes con formato incorrecto. La propiedad ActivityId del nodo Correlation en el encabezado del mensaje del evento se puede utilizar para determinar la actividad con errores. Para habilitar el seguimiento del flujo de mensajes por Id. de actividad, consulte [Configuring Message Flow Tracing](../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md). En este tema se muestra cómo habilitar el seguimiento del flujo de mensajes en el proyecto creado en el tutorial de introducción.

### <a name="to-enable-message-flow-tracing-in-the-getting-started-tutorial"></a>Para habilitar el seguimiento del flujo de mensajes en el tutorial de introducción

1. Abra el Visor de eventos, haga clic en **iniciar**, **ejecutar**y escriba `eventvwr.exe`.

2. Si no ha habilitado la traza analítica, expanda **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **aplicaciones de servidor de aplicaciones** . Seleccione **vista**, **mostrar analítico y depurar registros**. Haga clic en **analítico** y seleccione **Habilitar registro**. Deje el Visor de eventos abierto para que se puedan ver los seguimientos.

3. Abra el ejemplo creado en el [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md) en Visual Studio 2012. Tenga en cuenta que debe ejecutar Visual Studio 2012 como administrador para que se puede crear el servicio. Si ha instalado los ejemplos de WCF, puede abrir el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md), que contiene el proyecto completado creado en el tutorial.

4. Haga clic en el **servicio** del proyecto y seleccione **agregar**, **nuevo elemento**. Seleccione **archivo de configuración de aplicación** y haga clic en **Aceptar**.

5. Agregue el siguiente código al archivo App.Config creado en el paso anterior.

    ```xml
    <system.serviceModel>
      <diagnostics>
        <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>
      </diagnostics>
    </system.serviceModel>
    ```

6. Ejecute la aplicación de servidor sin depurar presionando CTRL+F5. Ejecutar el proyecto cliente haciendo clic con el **cliente** proyecto y seleccionaremos **depurar**, **Iniciar nueva instancia**.

7. Para realizar el seguimiento de los eventos del cliente al servidor, agregue lo siguiente al archivo de configuración de la aplicación en el proyecto Cliente.

    ```xml
    <diagnostics>
      <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>
    </diagnostics>
    ```

8. En Program.cs, en el cliente, agregue la siguiente instrucción Using.

    ```csharp
    using System.Diagnostics;
    ```

9. En el método Main del archivo program.cs del proyecto de cliente, establezca el GUID de seguimiento para que se propague en el registro de eventos.

    ```csharp
    Guid guid = Guid.NewGuid();
    Trace.CorrelationManager.ActivityId = guid;
    ```

10. Actualice y examine el **analítico** registro.  Busque un evento con el identificador de evento 220.  Seleccione el evento y haga clic en el **detalles** ficha en el panel de vista previa. Este evento contendrá el identificador de correlación de la actividad de llamada.

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
