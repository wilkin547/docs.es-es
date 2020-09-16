---
title: Participantes de seguimiento
ms.date: 03/30/2017
ms.assetid: f13e360c-eeb7-4a49-98a0-8f6a52d64f68
ms.openlocfilehash: 9455524da4451bf904d8449412e8f625542a1635
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551457"
---
# <a name="tracking-participants"></a><span data-ttu-id="3ba6a-102">Participantes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3ba6a-102">Tracking Participants</span></span>
<span data-ttu-id="3ba6a-103">Los participantes de seguimiento son puntos de extensibilidad que permiten a un desarrollador de flujo de trabajo tener acceso a objetos <xref:System.Activities.Tracking.InteropTrackingRecord.TrackingRecord%2A> y procesarlos.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-103">Tracking participants are extensibility points that allow a workflow developer to access <xref:System.Activities.Tracking.InteropTrackingRecord.TrackingRecord%2A> objects and process them.</span></span> [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <span data-ttu-id="3ba6a-104">incluye un participante de seguimiento estándar que escribe los registros de seguimiento como eventos de Seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="3ba6a-104">includes a standard tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span> <span data-ttu-id="3ba6a-105">Si eso no cumple sus requisitos, también puede escribir un participante de seguimiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-105">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="tracking-participants"></a><span data-ttu-id="3ba6a-106">Participantes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3ba6a-106">Tracking Participants</span></span>  
 <span data-ttu-id="3ba6a-107">La infraestructura de seguimiento permite la aplicación de un filtro en los registros de seguimiento salientes de forma que un participante pueda suscribirse a un subconjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-107">The tracking infrastructure allows the application of a filter on the outgoing tracking records such that a participant can subscribe to a subset of the records.</span></span> <span data-ttu-id="3ba6a-108">El mecanismo para aplicar un filtro es a través de un perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-108">The mechanism to apply a filter is through a tracking profile.</span></span>  
  
 <span data-ttu-id="3ba6a-109">Windows Workflow Foundation (WF) de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] proporciona un participante de seguimiento que escribe los registros de seguimiento en una sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-109">Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] provides a tracking participant that writes the tracking records to an ETW session.</span></span> <span data-ttu-id="3ba6a-110">El participante se configura en un servicio de flujo de trabajo agregando un comportamiento específico del seguimiento en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-110">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="3ba6a-111">Habilitar un participante de seguimiento de ETW permite realizar un seguimiento de los registros que se van a ver en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-111">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="3ba6a-112">El ejemplo de SDK para el seguimiento basado en ETW es una buena manera de familiarizarse con el seguimiento de WF mediante el participante de seguimiento basado en ETW.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-112">The SDK sample for ETW-based tracking is a good way to get familiar with WF tracking using the ETW-based tracking participant.</span></span>  
  
## <a name="etw-tracking-participant"></a><span data-ttu-id="3ba6a-113">Participante de seguimiento de ETW</span><span class="sxs-lookup"><span data-stu-id="3ba6a-113">ETW Tracking Participant</span></span>  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <span data-ttu-id="3ba6a-114">incluye un participante de seguimiento de ETW que escribe los registros de seguimiento en una sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-114">includes an ETW Tracking Participant that writes the tracking records to an ETW session.</span></span> <span data-ttu-id="3ba6a-115">Esto se realiza de una manera muy eficaz con un impacto mínimo en el rendimiento de la aplicación o en la capacidad de proceso del servidor.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-115">This is done in a very efficient manner with minimal impact to the application’s performance or to the server’s throughput.</span></span> <span data-ttu-id="3ba6a-116">La ventaja de usar el participante de seguimiento de ETW estándar es que los registros de seguimiento que recibe se pueden ver en la otra aplicación y en los registros del sistema en el Visor de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-116">An advantage of using the standard ETW tracking participant is that the tracking records it receives can be viewed with the other application and system logs in the Windows Event Viewer.</span></span>  
  
 <span data-ttu-id="3ba6a-117">El participante de seguimiento de ETW estándar está configurado en el archivo Web.config tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-117">The standard ETW tracking participant is configured in the Web.config file as shown in the following example.</span></span>  
  
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
> <span data-ttu-id="3ba6a-118">Si no se especifica un nombre de `trackingProfile`, como `<etwTracking/>` o `<etwTracking profileName=""/>`, se usa el perfil de seguimiento predeterminado instalado con [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] en el archivo Machine.config.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-118">If a `trackingProfile` name is not specified, such as just `<etwTracking/>` or `<etwTracking profileName=""/>`, then the default tracking profile installed with the [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] in the Machine.config file is used.</span></span>  
  
 <span data-ttu-id="3ba6a-119">En el archivo Machine.config, el perfil de seguimiento predeterminado se suscribe a los registros y errores de instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-119">In the Machine.config file, the default tracking profile subscribes to workflow instance records and faults.</span></span>  
  
 <span data-ttu-id="3ba6a-120">En ETW, los eventos se escriben en la sesión de ETW a través de un id. de proveedor.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-120">In ETW, events are written to the ETW session through a provider ID.</span></span> <span data-ttu-id="3ba6a-121">El id. de proveedor que el participante de seguimiento de ETW usa para escribir los registros de seguimiento en ETW se define en la sección de diagnóstico del archivo Web.config (debajo de `<system.serviceModel><diagnostics>`).</span><span class="sxs-lookup"><span data-stu-id="3ba6a-121">The provider ID that the ETW tracking participant uses for writing the tracking records to ETW is defined in the diagnostics section of the Web.config file (under `<system.serviceModel><diagnostics>`).</span></span> <span data-ttu-id="3ba6a-122">De forma predeterminada, el participante de seguimiento de ETW usa un id. de proveedor predeterminado cuando no se ha especificado uno, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-122">By default, the ETW tracking participant uses a default provider ID when one has not been specified, as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
        <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />  
```  
  
 <span data-ttu-id="3ba6a-123">La siguiente ilustración muestra el flujo de los datos de seguimiento a través del participante de seguimiento de ETW.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-123">The following illustration shows the flow of tracking data through the ETW tracking participant.</span></span> <span data-ttu-id="3ba6a-124">Una vez que los datos de seguimiento llegan a la sesión de ETW, se puede tener acceso a ellos de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-124">Once the tracking data reaches the ETW session, it can be accessed in a number of ways.</span></span> <span data-ttu-id="3ba6a-125">Una de las maneras más útiles de tener acceso a estos eventos es a través del visor de eventos, una herramienta común de Windows para ver registros y trazas de aplicaciones y servicios.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-125">One of the most useful ways to access these events is through Event Viewer, a common Windows tool used for viewing logs and traces from applications and services.</span></span>  
  
 ![Flujo de datos de seguimiento a través del proveedor de seguimiento de ETW.](./media/tracking-participants/tracking-data-event-tracing-windows-provider.gif)  
  
## <a name="tracking-participant-event-data"></a><span data-ttu-id="3ba6a-127">Datos de eventos del participante de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3ba6a-127">Tracking Participant Event Data</span></span>  
 <span data-ttu-id="3ba6a-128">Un participante del seguimiento serializa los datos de eventos a los que se ha realizado el seguimiento en una sesión de ETW con el formato de un evento por registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-128">A tracking participant serializes tracked event data to an ETW session in the format of one event per tracking record.</span></span>  <span data-ttu-id="3ba6a-129">Un evento se identifica mediante un id. en un intervalo entre 100 y 199.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-129">An event is identified using an ID within the range of 100 through 199.</span></span> <span data-ttu-id="3ba6a-130">Para obtener definiciones de los registros de eventos de seguimiento emitidos por un participante de seguimiento, vea el tema de [referencia sobre eventos de seguimiento](tracking-events-reference.md) .</span><span class="sxs-lookup"><span data-stu-id="3ba6a-130">For definitions of the tracking event records emitted by a tracking participant, see the [Tracking Events Reference](tracking-events-reference.md) topic.</span></span>  
  
 <span data-ttu-id="3ba6a-131">El tamaño de un evento ETW está limitado por el tamaño de búfer de ETW o por la carga máxima para un evento ETW, sea cual sea el valor más pequeño.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-131">The size of an ETW event is limited by the ETW buffer size, or the by the maximum payload for an ETW event, whichever value is smaller.</span></span> <span data-ttu-id="3ba6a-132">Si el tamaño del evento supera cualquiera de estos límites de ETW, el evento se trunca y se quita contenido de forma arbitraria.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-132">If the size of the event exceeds either of these ETW limits, the event is truncated and its content removed in an arbitrary manner.</span></span> <span data-ttu-id="3ba6a-133">No se quitan de forma selectiva variables, argumentos, anotaciones y datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-133">Variables, arguments, annotations and custom data are not selectively removed.</span></span> <span data-ttu-id="3ba6a-134">En caso de truncamiento, se truncan todos ellos independientemente del valor que provocó que el tamaño del evento superara el límite de ETW.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-134">In the case of truncation, all of these are truncated regardless of the value that caused the event size to exceed the ETW limit.</span></span>  <span data-ttu-id="3ba6a-135">Los datos quitados se reemplazan con `<item>..<item>`.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-135">The removed data is replaced with `<item>..<item>`.</span></span>  
  
 <span data-ttu-id="3ba6a-136">Los tipos complejos en variables, argumentos y elementos de datos personalizados se serializan en el registro de eventos de ETW mediante la <xref:System.Runtime.Serialization.NetDataContractSerializer> clase.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-136">Complex types in variables, arguments, and custom data items are serialized to the ETW event record using the <xref:System.Runtime.Serialization.NetDataContractSerializer> class.</span></span> <span data-ttu-id="3ba6a-137">Esta clase incluye información de tipo CLR en la secuencia XML serializada.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-137">This class includes CLR-type information in the serialized XML steam.</span></span>  
  
 <span data-ttu-id="3ba6a-138">El truncamiento de los datos de carga debido a los límites de ETW puede dar como resultado registros de seguimiento duplicados que se envían a una sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-138">Truncation of payload data due to ETW limits can result in duplicate tracking records being sent to an ETW session.</span></span> <span data-ttu-id="3ba6a-139">Esto se puede producir si hay más de una sesión que está escuchando los eventos y las sesiones tienen distintos límites de carga para los eventos.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-139">This can occur if more than one session is listening for the events and the sessions have different payload limits for the events.</span></span>  
  
 <span data-ttu-id="3ba6a-140">En el caso de la sesión con el límite inferior, el evento puede truncarse.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-140">For  the session with the lower limit the event may be truncated.</span></span> <span data-ttu-id="3ba6a-141">El participante de seguimiento de ETW no tiene conocimiento del número de sesiones que están escuchando los eventos. Si un evento se trunca para una sesión, el participante de ETW reintenta el envío del evento una vez.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-141">The ETW tracking participant does not have any knowledge of the number of sessions listening for the events; if an event is truncated for a session then the ETW participant retries sending the event once.</span></span> <span data-ttu-id="3ba6a-142">En este caso la sesión que se configura para aceptar un tamaño de carga mayor obtendrá el evento dos veces (el evento no truncado y el truncado).</span><span class="sxs-lookup"><span data-stu-id="3ba6a-142">In this case the session that is configured to accept a larger payload size will get the event twice (the non-truncated and truncated event).</span></span> <span data-ttu-id="3ba6a-143">Se puede evitar la duplicación configurando todas las sesiones ETW con los mismos límites del tamaño de búfer.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-143">Duplication can be prevented by configuring all the ETW sessions with same buffer size limits.</span></span>  
  
## <a name="accessing-tracking-data-from-an-etw-participant-in-the-event-viewer"></a><span data-ttu-id="3ba6a-144">Tener acceso a datos de seguimiento desde un participante de ETW en el visor de eventos</span><span class="sxs-lookup"><span data-stu-id="3ba6a-144">Accessing Tracking Data from an ETW Participant in the Event Viewer</span></span>  
 <span data-ttu-id="3ba6a-145">Se puede tener acceso a los eventos que un participante de seguimiento de ETW escribe en una sesión de ETW mediante el visor de eventos (cuando se usa el id. de proveedor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="3ba6a-145">Events that are written to an ETW session by the ETW tracking participant can be accessed through the Event Viewer (when using the default provider ID).</span></span> <span data-ttu-id="3ba6a-146">Esto permite ver rápidamente los registros de seguimiento que el flujo de trabajo haya emitido.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-146">This allows for rapidly viewing of tracking records that have been emitted by the workflow.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ba6a-147">Los eventos del registro de seguimiento emitidos en una sesión de ETW, usan id. de eventos en un intervalo de 100 a 199.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-147">Tracking record events emitted to an ETW session use event IDs in the range of 100 through 199.</span></span>  
  
#### <a name="to-enable-viewing-the-tracking-records-in-event-viewer"></a><span data-ttu-id="3ba6a-148">Para habilitar la visualización de los registros de seguimiento en el visor de eventos</span><span class="sxs-lookup"><span data-stu-id="3ba6a-148">To enable viewing the Tracking Records in Event Viewer</span></span>  
  
1. <span data-ttu-id="3ba6a-149">Inicie el visor de eventos (EVENTVWR.EXE)</span><span class="sxs-lookup"><span data-stu-id="3ba6a-149">Start the Event Viewer (EVENTVWR.EXE)</span></span>  
  
2. <span data-ttu-id="3ba6a-150">Seleccione **visor de eventos, registros de aplicaciones y servicios, Microsoft, Windows, servidor de aplicaciones-aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-150">Select **Event Viewer, Applications and Services Logs, Microsoft, Windows, Application Server-Applications**.</span></span>  
  
3. <span data-ttu-id="3ba6a-151">Haga clic con el botón derecho y asegúrese de que la opción **ver, Mostrar registros analíticos y de depuración** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-151">Right-click and ensure that **View, Show Analytic and Debug logs** is selected.</span></span> <span data-ttu-id="3ba6a-152">Si no, seleccione la opción de manera que la marca de verificación aparezca junto a ella.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-152">If not, select it so the check mark appears next to it.</span></span> <span data-ttu-id="3ba6a-153">Esto muestra los registros de **análisis**, **rendimiento**y **depuración** .</span><span class="sxs-lookup"><span data-stu-id="3ba6a-153">This displays the **Analytic**, **Perf**, and **Debug** logs.</span></span>  
  
4. <span data-ttu-id="3ba6a-154">Haga clic con el botón derecho en el registro **analítico** y seleccione **Habilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-154">Right-click the **Analytic** log and then select **Enable Log**.</span></span> <span data-ttu-id="3ba6a-155">El registro existirá en el archivo %SystemRoot%\System32\Winevt\Logs\Microsoft-Windows-Application Server-Applications%4Analytic.etl.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-155">The log will exist in the %SystemRoot%\System32\Winevt\Logs\Microsoft-Windows-Application Server-Applications%4Analytic.etl file.</span></span>  
  
## <a name="custom-tracking-participant"></a><span data-ttu-id="3ba6a-156">Participante de seguimiento personalizado</span><span class="sxs-lookup"><span data-stu-id="3ba6a-156">Custom Tracking Participant</span></span>  
 <span data-ttu-id="3ba6a-157">La API de participante de seguimiento permite la ampliación del tiempo de ejecución de seguimiento mediante un participante de seguimiento proporcionado por el usuario que puede incluir una lógica personalizada para controlar los registros de seguimiento emitidos por el tiempo de ejecución del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-157">The tracking participant API allows extension of the tracking runtime with a user-provided tracking participant that can include custom logic to handle tracking records emitted by the workflow runtime.</span></span> <span data-ttu-id="3ba6a-158">Para escribir un participante de seguimiento personalizado, el desarrollador de software debe implementar el método `Track` en la clase <xref:System.Activities.Tracking.TrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-158">To write a custom tracking participant, the developer must implement the `Track` method on the <xref:System.Activities.Tracking.TrackingParticipant> class.</span></span> <span data-ttu-id="3ba6a-159">Se llama a este método cuando el tiempo de ejecución emite un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-159">This method is called when a tracking record is emitted by the workflow runtime.</span></span>  
  
 <span data-ttu-id="3ba6a-160">Los participantes de seguimiento se derivan de la clase <xref:System.Activities.Tracking.TrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-160">Tracking participants derive from the <xref:System.Activities.Tracking.TrackingParticipant> class.</span></span> <span data-ttu-id="3ba6a-161">La clase <xref:System.Activities.Tracking.EtwTrackingParticipant> proporcionada por el sistema emite un evento ETW (Seguimiento de eventos para Windows) para cada registro de seguimiento que se haya recibido.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-161">The system-provided <xref:System.Activities.Tracking.EtwTrackingParticipant> emits an Event Tracking for Windows (ETW) event for each tracking record that is received.</span></span> <span data-ttu-id="3ba6a-162">Para crear un participante de seguimiento personalizado, se crea una clase que deriva de <xref:System.Activities.Tracking.TrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-162">To create a custom tracking participant, a class is created that derives from <xref:System.Activities.Tracking.TrackingParticipant>.</span></span> <span data-ttu-id="3ba6a-163">Para proporcionar funcionalidad básica de seguimiento, invalide <xref:System.Activities.Tracking.TrackingParticipant.Track%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-163">To provide basic tracking functionality, override <xref:System.Activities.Tracking.TrackingParticipant.Track%2A>.</span></span> <span data-ttu-id="3ba6a-164">Se llama a <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> cuando el tiempo de ejecución envía un registro de seguimiento que se puede procesar de la manera deseada.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-164"><xref:System.Activities.Tracking.TrackingParticipant.Track%2A> is called when a tracking record is sent by the runtime and can be processed in the desired manner.</span></span> <span data-ttu-id="3ba6a-165">En el siguiente ejemplo, se define una clase de participante de seguimiento personalizada que emite todos los registros de seguimiento en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-165">In the following example, a custom tracking participant class is defined that emits all tracking records to the console window.</span></span> <span data-ttu-id="3ba6a-166">También puede implementar un objeto <xref:System.Activities.Tracking.TrackingParticipant> que procesa los registros de seguimiento de forma asincrónica mediante los métodos `BeginTrack` y `EndTrack`.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-166">You can also implement a <xref:System.Activities.Tracking.TrackingParticipant> object that processes the tracking records asynchronously using its `BeginTrack` and `EndTrack` methods</span></span>  
  
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
  
 <span data-ttu-id="3ba6a-167">Para usar un participante de seguimiento concreto, regístrelo con la instancia de flujo de trabajo a la que desea realizar el seguimiento, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-167">To use a particular tracking participant, register it with the workflow instance that you want to track, as shown in the following example.</span></span>  
  
```csharp  
myInstance.Extensions.Add(new ConsoleTrackingParticipant());  
```  
  
 <span data-ttu-id="3ba6a-168">En el ejemplo siguiente, se crea un flujo de trabajo que está compuesto de una actividad <xref:System.Activities.Statements.Sequence> que contiene una actividad <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-168">In the following example, a workflow that consists of a <xref:System.Activities.Statements.Sequence> activity that contains a <xref:System.Activities.Statements.WriteLine> activity is created.</span></span> <span data-ttu-id="3ba6a-169">`ConsoleTrackingParticipant` se agrega a las extensiones y después se invoca el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3ba6a-169">The `ConsoleTrackingParticipant` is added to the extensions and the workflow is invoked.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3ba6a-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ba6a-170">See also</span></span>

- <span data-ttu-id="3ba6a-171">[Supervisión de Windows Server App fabric](/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="3ba6a-171">[Windows Server App Fabric Monitoring](/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="3ba6a-172">[Supervisión de aplicaciones con App fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="3ba6a-172">[Monitoring Applications with App Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
