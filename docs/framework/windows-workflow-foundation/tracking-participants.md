---
title: Participantes de seguimiento
ms.date: 03/30/2017
ms.assetid: f13e360c-eeb7-4a49-98a0-8f6a52d64f68
ms.openlocfilehash: a033b65125a562307c6247eeda93dcacb31f5382
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837654"
---
# <a name="tracking-participants"></a>Participantes de seguimiento
Los participantes de seguimiento son puntos de extensibilidad que permiten a un desarrollador de flujo de trabajo tener acceso a objetos <xref:System.Activities.Tracking.InteropTrackingRecord.TrackingRecord%2A> y procesarlos. [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] incluye un participante de seguimiento estándar que escribe los registros de seguimiento como eventos de Seguimiento de eventos para Windows (ETW). Si eso no cumple sus requisitos, también puede escribir un participante de seguimiento personalizado.  
  
## <a name="tracking-participants"></a>Participantes de seguimiento  
 La infraestructura de seguimiento permite la aplicación de un filtro en los registros de seguimiento salientes de forma que un participante pueda suscribirse a un subconjunto de registros. El mecanismo para aplicar un filtro es a través de un perfil de seguimiento.  
  
 Windows Workflow Foundation (WF) en [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] proporciona un participante de seguimiento que escribe los registros de seguimiento en una sesión de ETW. El participante se configura en un servicio de flujo de trabajo agregando un comportamiento específico del seguimiento en un archivo de configuración. Habilitar un participante de seguimiento de ETW permite realizar un seguimiento de los registros que se van a ver en el visor de eventos. El ejemplo de SDK para el seguimiento basado en ETW es una buena manera de familiarizarse con el seguimiento de WF mediante el participante de seguimiento basado en ETW.  
  
## <a name="etw-tracking-participant"></a>Participante de seguimiento de ETW  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] incluye un participante de seguimiento de ETW que escribe los registros de seguimiento en una sesión de ETW. Esto se realiza de una manera muy eficaz con un impacto mínimo en el rendimiento de la aplicación o en la capacidad de proceso del servidor. La ventaja de usar el participante de seguimiento de ETW estándar es que los registros de seguimiento que recibe se pueden ver en la otra aplicación y en los registros del sistema en el Visor de eventos de Windows.  
  
 El participante de seguimiento de ETW estándar está configurado en el archivo Web.config tal y como se muestra en el siguiente ejemplo.  
  
```xml  
<configuration>  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
   <tracking>  
      <profiles>  
        <trackingProfile name="Sample Tracking Profile">  
        ….  
       </trackingProfile>  
      </profiles>  
    </tracking>  
  </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
> Si no se especifica un nombre de `trackingProfile`, como `<etwTracking/>` o `<etwTracking profileName=""/>`, se usa el perfil de seguimiento predeterminado instalado con [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] en el archivo Machine.config.  
  
 En el archivo Machine.config, el perfil de seguimiento predeterminado se suscribe a los registros y errores de instancias de flujo de trabajo.  
  
 En ETW, los eventos se escriben en la sesión de ETW a través de un id. de proveedor. El id. de proveedor que el participante de seguimiento de ETW usa para escribir los registros de seguimiento en ETW se define en la sección de diagnóstico del archivo Web.config (debajo de `<system.serviceModel><diagnostics>`). De forma predeterminada, el participante de seguimiento de ETW usa un id. de proveedor predeterminado cuando no se ha especificado uno, tal y como se muestra en el siguiente ejemplo.  
  
```xml  
<system.serviceModel>  
        <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />  
```  
  
 La siguiente ilustración muestra el flujo de los datos de seguimiento a través del participante de seguimiento de ETW. Una vez que los datos de seguimiento llegan a la sesión de ETW, se puede tener acceso a ellos de varias maneras. Una de las maneras más útiles de tener acceso a estos eventos es a través del visor de eventos, una herramienta común de Windows para ver registros y trazas de aplicaciones y servicios.  
  
 ![Flujo de datos de seguimiento a través del proveedor de seguimiento de ETW.](./media/tracking-participants/tracking-data-event-tracing-windows-provider.gif)  
  
## <a name="tracking-participant-event-data"></a>Datos de eventos del participante de seguimiento  
 Un participante del seguimiento serializa los datos de eventos a los que se ha realizado el seguimiento en una sesión de ETW con el formato de un evento por registro de seguimiento.  Un evento se identifica mediante un id. en un intervalo entre 100 y 199. Para obtener definiciones de los registros de eventos de seguimiento emitidos por un participante de seguimiento, vea el tema de [referencia sobre eventos de seguimiento](tracking-events-reference.md) .  
  
 El tamaño de un evento ETW está limitado por el tamaño de búfer de ETW o por la carga máxima para un evento ETW, sea cual sea el valor más pequeño. Si el tamaño del evento supera cualquiera de estos límites de ETW, el evento se trunca y se quita contenido de forma arbitraria. No se quitan de forma selectiva variables, argumentos, anotaciones y datos personalizados. En caso de truncamiento, se truncan todos ellos independientemente del valor que provocó que el tamaño del evento superara el límite de ETW.  Los datos quitados se reemplazan con `<item>..<item>`.  
  
 Los tipos complejos en variables, argumentos y elementos de datos personalizados se serializan en el registro de eventos de ETW mediante la clase <xref:System.Runtime.Serialization.NetDataContractSerializer>. Esta clase incluye información de tipo CLR en la secuencia XML serializada.  
  
 El truncamiento de los datos de carga debido a los límites de ETW puede dar como resultado registros de seguimiento duplicados que se envían a una sesión de ETW. Esto se puede producir si hay más de una sesión que está escuchando los eventos y las sesiones tienen distintos límites de carga para los eventos.  
  
 En el caso de la sesión con el límite inferior, el evento puede truncarse. El participante de seguimiento de ETW no tiene conocimiento del número de sesiones que están escuchando los eventos. Si un evento se trunca para una sesión, el participante de ETW reintenta el envío del evento una vez. En este caso la sesión que se configura para aceptar un tamaño de carga mayor obtendrá el evento dos veces (el evento no truncado y el truncado). Se puede evitar la duplicación configurando todas las sesiones ETW con los mismos límites del tamaño de búfer.  
  
## <a name="accessing-tracking-data-from-an-etw-participant-in-the-event-viewer"></a>Tener acceso a datos de seguimiento desde un participante de ETW en el visor de eventos  
 Se puede tener acceso a los eventos que un participante de seguimiento de ETW escribe en una sesión de ETW mediante el visor de eventos (cuando se usa el id. de proveedor predeterminado). Esto permite ver rápidamente los registros de seguimiento que el flujo de trabajo haya emitido.  
  
> [!NOTE]
> Los eventos del registro de seguimiento emitidos en una sesión de ETW, usan id. de eventos en un intervalo de 100 a 199.  
  
#### <a name="to-enable-viewing-the-tracking-records-in-event-viewer"></a>Para habilitar la visualización de los registros de seguimiento en el visor de eventos  
  
1. Inicie el visor de eventos (EVENTVWR.EXE)  
  
2. Seleccione **visor de eventos, registros de aplicaciones y servicios, Microsoft, Windows, servidor de aplicaciones-aplicaciones**.  
  
3. Haga clic con el botón derecho y asegúrese de que la opción **ver, Mostrar registros analíticos y de depuración** está seleccionada. Si no, seleccione la opción de manera que la marca de verificación aparezca junto a ella. Esto muestra los registros de **análisis**, **rendimiento**y **depuración** .  
  
4. Haga clic con el botón derecho en el registro **analítico** y seleccione **Habilitar registro**. El registro existirá en el archivo %SystemRoot%\System32\Winevt\Logs\Microsoft-Windows-Application Server-Applications%4Analytic.etl.  
  
## <a name="custom-tracking-participant"></a>Participante de seguimiento personalizado  
 La API de participante de seguimiento permite la ampliación del tiempo de ejecución de seguimiento mediante un participante de seguimiento proporcionado por el usuario que puede incluir una lógica personalizada para controlar los registros de seguimiento emitidos por el tiempo de ejecución del flujo de trabajo. Para escribir un participante de seguimiento personalizado, el desarrollador de software debe implementar el método `Track` en la clase <xref:System.Activities.Tracking.TrackingParticipant>. Se llama a este método cuando el tiempo de ejecución emite un registro de seguimiento.  
  
 Los participantes de seguimiento se derivan de la clase <xref:System.Activities.Tracking.TrackingParticipant>. La clase <xref:System.Activities.Tracking.EtwTrackingParticipant> proporcionada por el sistema emite un evento ETW (Seguimiento de eventos para Windows) para cada registro de seguimiento que se haya recibido. Para crear un participante de seguimiento personalizado, se crea una clase que deriva de <xref:System.Activities.Tracking.TrackingParticipant>. Para proporcionar funcionalidad básica de seguimiento, invalide <xref:System.Activities.Tracking.TrackingParticipant.Track%2A>. Se llama a <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> cuando el tiempo de ejecución envía un registro de seguimiento que se puede procesar de la manera deseada. En el siguiente ejemplo, se define una clase de participante de seguimiento personalizada que emite todos los registros de seguimiento en la ventana de la consola. También puede implementar un objeto <xref:System.Activities.Tracking.TrackingParticipant> que procesa los registros de seguimiento de forma asincrónica mediante los métodos `BeginTrack` y `EndTrack`.  
  
```csharp  
class ConsoleTrackingParticipant : TrackingParticipant  
{  
    protected override void Track(TrackingRecord record, TimeSpan timeout)  
    {  
        if (record != null)  
        {  
            Console.WriteLine("=================================");  
            Console.WriteLine(record);  
        }  
    }  
}  
```  
  
 Para usar un participante de seguimiento concreto, regístrelo con la instancia de flujo de trabajo a la que desea realizar el seguimiento, tal y como se muestra en el siguiente ejemplo.  
  
```csharp  
myInstance.Extensions.Add(new ConsoleTrackingParticipant());  
```  
  
 En el ejemplo siguiente, se crea un flujo de trabajo que está compuesto de una actividad <xref:System.Activities.Statements.Sequence> que contiene una actividad <xref:System.Activities.Statements.WriteLine>. `ConsoleTrackingParticipant` se agrega a las extensiones y después se invoca el flujo de trabajo.  
  
```csharp  
Activity activity= new Sequence()  
{  
    Activities =  
    {  
        new WriteLine()  
        {  
            Text = "Hello World."  
        }  
    }  
};  
  
WorkflowApplication instance = new WorkflowApplication(activity);  
  
instance.Extensions.Add(new ConsoleTrackingParticipant());  
  instance.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
            {  
                Console.WriteLine("workflow instance completed, Id = " + instance.Id);  
                resetEvent.Set();  
            };  
            instance.Run();  
            Console.ReadLine();  
```  
  
## <a name="see-also"></a>Vea también

- [Supervisión de Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))
- [Supervisión de aplicaciones con App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))
