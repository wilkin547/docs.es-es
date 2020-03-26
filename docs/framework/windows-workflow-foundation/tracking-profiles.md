---
title: Perfiles de seguimiento
ms.date: 03/30/2017
ms.assetid: 22682566-1cd9-4672-9791-fb3523638e18
ms.openlocfilehash: 609c3f0c728e71d1bbf5335aae0b18d6f99a7181
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249043"
---
# <a name="tracking-profiles"></a><span data-ttu-id="b38bb-102">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b38bb-102">Tracking Profiles</span></span>

<span data-ttu-id="b38bb-103">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b38bb-103">Tracking profiles contain tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span>

## <a name="tracking-profiles"></a><span data-ttu-id="b38bb-104">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b38bb-104">Tracking Profiles</span></span>

<span data-ttu-id="b38bb-105">Los perfiles de seguimiento se usan para especificar qué información de seguimiento se emite para una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b38bb-105">Tracking profiles are used to specify which tracking information is emitted for a workflow instance.</span></span> <span data-ttu-id="b38bb-106">Si no se especifica ningún perfil, se emiten todos los eventos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b38bb-106">If no profile is specified, then all tracking events are emitted.</span></span> <span data-ttu-id="b38bb-107">Si se especifica un perfil, se emitirán los eventos de seguimiento especificados en el perfil.</span><span class="sxs-lookup"><span data-stu-id="b38bb-107">If a profile is specified, then the tracking events specified in the profile will be emitted.</span></span> <span data-ttu-id="b38bb-108">Dependiendo de sus requisitos de supervisión, puede escribir un perfil que es muy general, que se suscribe a un conjunto pequeño de cambios de estado de alto nivel en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b38bb-108">Depending on your monitoring requirements, you may write a profile that is very general, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="b38bb-109">En cambio, puede crear un perfil muy detallado cuyos eventos resultantes estén lo suficientemente enriquecidos para reconstruir un flujo de ejecución detallado más adelante.</span><span class="sxs-lookup"><span data-stu-id="b38bb-109">Conversely, you may create a very detailed profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>

<span data-ttu-id="b38bb-110">Los perfiles de seguimiento se manifiestan como elementos XML dentro de un archivo de configuración estándar de .NET Framework o especificados en el código.</span><span class="sxs-lookup"><span data-stu-id="b38bb-110">Tracking profiles manifest themselves as XML elements within a standard .NET Framework configuration file or specified in code.</span></span> <span data-ttu-id="b38bb-111">El siguiente ejemplo es de un perfil de seguimiento de [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] en un archivo de configuración que permite a un participante de seguimiento suscribirse a los eventos de flujo de trabajo `Started` y `Completed`.</span><span class="sxs-lookup"><span data-stu-id="b38bb-111">The following example is of a [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>

```xml
<system.serviceModel>
    ...
    <tracking>
     <profiles>
      <trackingProfile name="Sample Tracking Profile">
        <workflow activityDefinitionId="*">
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="Started"/>
                <state name="Completed"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
    ...
</system.serviceModel>
```

<span data-ttu-id="b38bb-112">El ejemplo siguiente muestra el perfil de seguimiento equivalente creado mediante código.</span><span class="sxs-lookup"><span data-stu-id="b38bb-112">The following example shows the equivalent tracking profile created using code.</span></span>

```csharp
TrackingProfile profile = new TrackingProfile()
{
    Name = "CustomTrackingProfile",
    Queries =
    {
        new WorkflowInstanceQuery()
        {
            // Limit workflow instance tracking records for started and
            // completed workflow states.
            States = { WorkflowInstanceStates.Started, WorkflowInstanceStates.Completed },
        }
    }
};
```

<span data-ttu-id="b38bb-113">Los registros de seguimiento se filtran a través del modo de visibilidad dentro de un perfil de seguimiento mediante el atributo <xref:System.Activities.Tracking.ImplementationVisibility>.</span><span class="sxs-lookup"><span data-stu-id="b38bb-113">Tracking records are filtered through the visibility mode within a tracking profile by using the <xref:System.Activities.Tracking.ImplementationVisibility> attribute.</span></span> <span data-ttu-id="b38bb-114">Una actividad compuesta es una actividad de nivel superior que contiene otras actividades que forman su implementación.</span><span class="sxs-lookup"><span data-stu-id="b38bb-114">A composite activity is a top-level activity that contains other activities that form its implementation.</span></span> <span data-ttu-id="b38bb-115">El modo de visibilidad especifica los registros de seguimiento emitidos desde actividades compuestas dentro de una actividad de flujo de trabajo para especificar si se realiza el seguimiento de las actividades que forman la implementación.</span><span class="sxs-lookup"><span data-stu-id="b38bb-115">The visibility mode specifies the tracking records emitted from composite activities within a workflow activity, to specify if activities that form the implementation are being tracked.</span></span> <span data-ttu-id="b38bb-116">El modo de visibilidad se aplica en el nivel del perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b38bb-116">The visibility mode applies at the tracking profile level.</span></span> <span data-ttu-id="b38bb-117">Las consultas incluidas en el perfil de seguimiento controlan el filtrado de los registros de seguimiento para las actividades individuales dentro de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b38bb-117">The filtering of tracking records for individual activities within a workflow is controlled by the queries within the tracking profile.</span></span> <span data-ttu-id="b38bb-118">Para obtener más información, consulte la sección Tipos de consulta de perfil de **seguimiento** en este documento.</span><span class="sxs-lookup"><span data-stu-id="b38bb-118">For more information, see the **Tracking Profile Query Types** section in this document.</span></span>

<span data-ttu-id="b38bb-119">Los dos modos de visibilidad especificados por el atributo `implementationVisibility` en el perfil de seguimiento son `RootScope` y `All`.</span><span class="sxs-lookup"><span data-stu-id="b38bb-119">The two visibility modes specified by the `implementationVisibility` attribute in the tracking profile are `RootScope` and `All`.</span></span> <span data-ttu-id="b38bb-120">Al usar el modo `RootScope`, se suprimen los registros de seguimiento para las actividades que forman la implementación de una actividad en el caso de que una actividad compuesta no sea la raíz de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b38bb-120">Using the `RootScope` mode suppresses the tracking records for activities that form the implementation of an activity in the case where a composite activity is not the root of a workflow.</span></span> <span data-ttu-id="b38bb-121">Esto implica que, cuando una actividad que se implementa usando otras actividades se agrega a un flujo de trabajo y `implementationVisibility` está definido en RootScope, sólo se realiza el seguimiento de la actividad de nivel superior incluida en esa actividad compuesta.</span><span class="sxs-lookup"><span data-stu-id="b38bb-121">This implies that, when an activity that is implemented using other activities is added to a workflow, and the `implementationVisibility` set to RootScope, only the top-level activity within that composite activity is tracked.</span></span> <span data-ttu-id="b38bb-122">Si una actividad es la raíz del flujo de trabajo, la implementación de la actividad es el propio flujo de trabajo y los registros de seguimiento se emiten para actividades que forman la implementación.</span><span class="sxs-lookup"><span data-stu-id="b38bb-122">If an activity is the root of the workflow, then the implementation of the activity is the workflow itself and tracking records are emitted for activities that form the implementation.</span></span> <span data-ttu-id="b38bb-123">Gracias al modo All, se permite que todos los registros de seguimiento se emitan para la actividad raíz y todas sus actividades compuestas.</span><span class="sxs-lookup"><span data-stu-id="b38bb-123">Using the All mode permits all tracking records to be emitted for the root activity and all its composite activities.</span></span>

<span data-ttu-id="b38bb-124">Por ejemplo, supongamos que *MyActivity* es una actividad compuesta cuya implementación contiene dos actividades, *Activity1* y *Activity2*.</span><span class="sxs-lookup"><span data-stu-id="b38bb-124">For example, suppose *MyActivity* is a composite activity whose implementation contains two activities, *Activity1* and *Activity2*.</span></span> <span data-ttu-id="b38bb-125">Cuando esta actividad se agrega a un flujo de `implementationVisibility` trabajo `RootScope`y el seguimiento está habilitado con un perfil de seguimiento con establecido en , los registros de seguimiento se emiten solo para *MyActivity*.</span><span class="sxs-lookup"><span data-stu-id="b38bb-125">When this activity is added to a workflow and tracking is enabled with a tracking profile with `implementationVisibility` set to `RootScope`, tracking records are emitted only for *MyActivity*.</span></span> <span data-ttu-id="b38bb-126">Sin embargo, no se emite ningún registro para las actividades *Activity1* y *Activity2*.</span><span class="sxs-lookup"><span data-stu-id="b38bb-126">However, no records are emitted for activities *Activity1* and *Activity2*.</span></span>

<span data-ttu-id="b38bb-127">Sin embargo, si `implementationVisibility` el atributo `All`para el perfil de seguimiento se establece en , los registros de seguimiento se emiten no solo para *MyActivity*, sino también para las actividades *Activity1* y *Activity2*.</span><span class="sxs-lookup"><span data-stu-id="b38bb-127">However, if the `implementationVisibility` attribute for the tracking profile is  set to `All`, then tracking records are emitted not only for *MyActivity*, but also for activities *Activity1* and *Activity2*.</span></span>

<span data-ttu-id="b38bb-128">La marca `implementationVisibility` se aplica a los siguientes tipos de registro de seguimiento:</span><span class="sxs-lookup"><span data-stu-id="b38bb-128">The `implementationVisibility` flag applies to following tracking record types:</span></span>

- <span data-ttu-id="b38bb-129">ActivityStateRecord</span><span class="sxs-lookup"><span data-stu-id="b38bb-129">ActivityStateRecord</span></span>

- <span data-ttu-id="b38bb-130">FaultPropagationRecord</span><span class="sxs-lookup"><span data-stu-id="b38bb-130">FaultPropagationRecord</span></span>

- <span data-ttu-id="b38bb-131">CancelRequestedRecord</span><span class="sxs-lookup"><span data-stu-id="b38bb-131">CancelRequestedRecord</span></span>

- <span data-ttu-id="b38bb-132">ActivityScheduledRecord</span><span class="sxs-lookup"><span data-stu-id="b38bb-132">ActivityScheduledRecord</span></span>

> [!NOTE]
> <span data-ttu-id="b38bb-133">CustomTrackingRecords emitidos a partir de la implementación de actividad no se filtran por el valor implementationVisibility.</span><span class="sxs-lookup"><span data-stu-id="b38bb-133">CustomTrackingRecords emitted from activity implementation are not filtered out by the implementationVisibility setting.</span></span>

<span data-ttu-id="b38bb-134">La funcionalidad `implementationVisibility` se especifica como <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> en el perfil de seguimiento en código de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="b38bb-134">The `implementationVisibility` functionality is specified as <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> on the tracking profile in code as follows:</span></span>

```csharp
TrackingProfile sampleTrackingProfile = new TrackingProfile()
{
    Name = "Sample Tracking Profile",
    ImplementationVisibility = ImplementationVisibility.RootScope
};
```

<span data-ttu-id="b38bb-135">La funcionalidad `implementationVisibility` se especifica como <xref:System.Activities.Tracking.ImplementationVisibility.All> en el perfil de seguimiento en un archivo de configuración de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b38bb-135">The `implementationVisibility` functionality is specified as <xref:System.Activities.Tracking.ImplementationVisibility.All> on the tracking profile in a configuration file as follows:</span></span>

```xml
<tracking>
      <profiles>
        <trackingProfile name="Shipping Monitoring" implementationVisibility="All">
          <workflow activityDefinitionId="*">
...
         </workflow>
        </trackingProfile>
      </profiles>
</tracking>
```

<span data-ttu-id="b38bb-136">El valor `ImplementationVisibility` en el perfil de seguimiento es opcional.</span><span class="sxs-lookup"><span data-stu-id="b38bb-136">The `ImplementationVisibility` setting on the tracking profile is optional.</span></span> <span data-ttu-id="b38bb-137">De manera predeterminada, su valor está definido en `RootScope`.</span><span class="sxs-lookup"><span data-stu-id="b38bb-137">By default, its value is set to `RootScope`.</span></span> <span data-ttu-id="b38bb-138">Los valores para este atributo distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b38bb-138">The values for this attribute are also case-sensitive.</span></span>

### <a name="tracking-profile-query-types"></a><span data-ttu-id="b38bb-139">Tipos de consulta de perfil de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b38bb-139">Tracking Profile Query Types</span></span>

<span data-ttu-id="b38bb-140">Los perfiles de seguimiento se estructuran como suscripciones declarativas para los registros de seguimiento que le permiten consultar el tiempo de ejecución de flujo de trabajo para registros de seguimiento específicos.</span><span class="sxs-lookup"><span data-stu-id="b38bb-140">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="b38bb-141">Hay varios tipos de consulta que permiten que se suscriba a clases diferentes de objetos <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="b38bb-141">There are several query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="b38bb-142">Los perfiles de seguimiento se pueden especificar en la configuración o a través del código.</span><span class="sxs-lookup"><span data-stu-id="b38bb-142">Tracking profiles can be specified in configuration or through code.</span></span> <span data-ttu-id="b38bb-143">A continuación, se describen los tipos de consulta más comunes:</span><span class="sxs-lookup"><span data-stu-id="b38bb-143">Here are the most common query types:</span></span>

- <span data-ttu-id="b38bb-144"><xref:System.Activities.Tracking.WorkflowInstanceQuery>: úsela para realizar el seguimiento de los cambios de ciclo de vida de la instancia de flujo de trabajo como los valores `Started` y `Completed` mostrados previamente.</span><span class="sxs-lookup"><span data-stu-id="b38bb-144"><xref:System.Activities.Tracking.WorkflowInstanceQuery> - Use this to track workflow instance life cycle changes like the previously-demonstrated `Started` and `Completed`.</span></span> <span data-ttu-id="b38bb-145"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="b38bb-145">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>

  - <xref:System.Activities.Tracking.WorkflowInstanceRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>

  <span data-ttu-id="b38bb-146">Los estados a los que se puede suscribir se especifican en la clase <xref:System.Activities.Tracking.WorkflowInstanceStates>.</span><span class="sxs-lookup"><span data-stu-id="b38bb-146">The states that can be subscribed to are specified in the <xref:System.Activities.Tracking.WorkflowInstanceStates> class.</span></span>

  <span data-ttu-id="b38bb-147">La configuración o código usados para suscribirse a los registros de seguimiento en el nivel de instancia del flujo de trabajo correspondientes al estado de la instancia `Started` que usa <xref:System.Activities.Tracking.WorkflowInstanceQuery> se muestran en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b38bb-147">The configuration or code used to subscribe to workflow instance-level tracking records for the `Started` instance state using the <xref:System.Activities.Tracking.WorkflowInstanceQuery> is shown in the following example.</span></span>

  ```xml
  <workflowInstanceQueries>
      <workflowInstanceQuery>
        <states>
          <state name="Started"/>
        </states>
      </workflowInstanceQuery>
  </workflowInstanceQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new WorkflowInstanceQuery()
          {
              States = { WorkflowInstanceStates.Started}
          }
      }
  };
  ```

- <span data-ttu-id="b38bb-148"><xref:System.Activities.Tracking.ActivityStateQuery>: úsela para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b38bb-148"><xref:System.Activities.Tracking.ActivityStateQuery> - Use this to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="b38bb-149">Por ejemplo, es posible que desee realizar un seguimiento de cada vez que se complete la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b38bb-149">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="b38bb-150">Esta consulta es necesaria para que <xref:System.Activities.Tracking.TrackingParticipant> se suscriba a los objetos <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="b38bb-150">This query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.ActivityStateRecord> objects.</span></span> <span data-ttu-id="b38bb-151">Los estados de suscripción disponibles se especifican en <xref:System.Activities.Tracking.ActivityStates>.</span><span class="sxs-lookup"><span data-stu-id="b38bb-151">The available states to subscribe to are specified in <xref:System.Activities.Tracking.ActivityStates>.</span></span>

  <span data-ttu-id="b38bb-152">La configuración y el código usados para suscribirse a los registros de seguimiento del estado de la actividad que usan <xref:System.Activities.Tracking.ActivityStateQuery> para la actividad `SendEmailActivity` se muestran en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b38bb-152">The configuration and code used to subscribe activity state tracking records that use the <xref:System.Activities.Tracking.ActivityStateQuery> for the `SendEmailActivity` activity is shown in the following example.</span></span>

  ```xml
  <activityStateQueries>
    <activityStateQuery activityName="SendEmailActivity">
      <states>
        <state name="Closed"/>
      </states>
    </activityStateQuery>
  </activityStateQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new ActivityStateQuery()
          {
              ActivityName = "SendEmailActivity",
              States = { ActivityStates.Closed }
          }
      }
  };
  ```

  > [!NOTE]
  > <span data-ttu-id="b38bb-153">Si hay varios elementos activityStateQuery con el mismo nombre, solo se los estados del último elemento en el perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b38bb-153">If multiple activityStateQuery elements have the same name, only the states in the last element are used in the tracking profile.</span></span>

- <span data-ttu-id="b38bb-154"><xref:System.Activities.Tracking.ActivityScheduledQuery>: esta consulta le permite realizar el seguimiento de una actividad programada para que sea ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="b38bb-154"><xref:System.Activities.Tracking.ActivityScheduledQuery> - This query allows you to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="b38bb-155">La consulta es necesaria para que <xref:System.Activities.Tracking.TrackingParticipant> se suscriba a los objetos <xref:System.Activities.Tracking.ActivityScheduledRecord>.</span><span class="sxs-lookup"><span data-stu-id="b38bb-155">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.ActivityScheduledRecord> objects.</span></span>

  <span data-ttu-id="b38bb-156">La configuración y el código usados para suscribirse a los registros relacionados con la actividad secundaria `SendEmailActivity` que se está programando con <xref:System.Activities.Tracking.ActivityScheduledQuery> se muestran en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b38bb-156">The configuration and code used to subscribe to records related to the `SendEmailActivity` child activity being scheduled using the <xref:System.Activities.Tracking.ActivityScheduledQuery> is shown in the following example.</span></span>

  ```xml
  <activityScheduledQueries>
    <activityScheduledQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />
  </activityScheduledQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new ActivityScheduledQuery()
          {
              ActivityName = "ProcessNotificationsActivity",
              ChildActivityName = "SendEmailActivity"
          }
      }
  };
  ```

- <span data-ttu-id="b38bb-157"><xref:System.Activities.Tracking.FaultPropagationQuery>: use este valor para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="b38bb-157"><xref:System.Activities.Tracking.FaultPropagationQuery> - Use this to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="b38bb-158">La consulta es necesaria para que <xref:System.Activities.Tracking.TrackingParticipant> se suscriba a los objetos <xref:System.Activities.Tracking.FaultPropagationRecord>.</span><span class="sxs-lookup"><span data-stu-id="b38bb-158">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.FaultPropagationRecord> objects.</span></span>

  <span data-ttu-id="b38bb-159">La configuración y el código que se usen para suscribirse a registros relacionados con la propagación de errores mediante <xref:System.Activities.Tracking.FaultPropagationQuery> se muestran en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b38bb-159">The configuration and code used to subscribe to records related to fault propagation using <xref:System.Activities.Tracking.FaultPropagationQuery> is shown in the following example.</span></span>

  ```xml
  <faultPropagationQueries>
    <faultPropagationQuery faultSourceActivityName="SendEmailActivity" faultHandlerActivityName="NotificationsFaultHandler" />
  </faultPropagationQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new FaultPropagationQuery()
          {
              FaultSourceActivityName = "SendEmailActivity",
              FaultHandlerActivityName = "NotificationsFaultHandler"
          }
      }
  };
  ```

- <span data-ttu-id="b38bb-160"><xref:System.Activities.Tracking.CancelRequestedQuery>: úsela para realizar un seguimiento de las solicitudes para cancelar una actividad secuncaria mediante la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="b38bb-160"><xref:System.Activities.Tracking.CancelRequestedQuery> - Use this to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="b38bb-161">La consulta es necesaria para que <xref:System.Activities.Tracking.TrackingParticipant> se suscriba a los objetos <xref:System.Activities.Tracking.CancelRequestedRecord>.</span><span class="sxs-lookup"><span data-stu-id="b38bb-161">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.CancelRequestedRecord> objects.</span></span>

  <span data-ttu-id="b38bb-162">La configuración y el código utilizados para <xref:System.Activities.Tracking.CancelRequestedQuery> suscribirse a registros relacionados con la cancelación de actividad mediante se muestran en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b38bb-162">The configuration and code used to subscribe to records related to activity cancellation using <xref:System.Activities.Tracking.CancelRequestedQuery> is shown in the following example.</span></span>

  ```xml
  <cancelRequestedQueries>
    <cancelRequestedQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />
  </cancelRequestedQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new CancelRequestedQuery()
          {
              ActivityName = "ProcessNotificationsActivity",
              ChildActivityName = "SendEmailActivity"
          }
      }
  };
  ```

- <span data-ttu-id="b38bb-163"><xref:System.Activities.Tracking.CustomTrackingQuery>: úsela para realizar el seguimiento de eventos que defina en las actividades de código.</span><span class="sxs-lookup"><span data-stu-id="b38bb-163"><xref:System.Activities.Tracking.CustomTrackingQuery> - Use this to track events that you define in your code activities.</span></span> <span data-ttu-id="b38bb-164">La consulta es necesaria para que <xref:System.Activities.Tracking.TrackingParticipant> se suscriba a los objetos <xref:System.Activities.Tracking.CustomTrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="b38bb-164">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.CustomTrackingRecord> objects.</span></span>

  <span data-ttu-id="b38bb-165">La configuración y el código usados para suscribirse a los registros relacionados con los registros de seguimiento personalizados mediante <xref:System.Activities.Tracking.CustomTrackingQuery> se muestran en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b38bb-165">The configuration and code used to subscribe to records related to custom tracking records using <xref:System.Activities.Tracking.CustomTrackingQuery> is shown in the following example.</span></span>

  ```xml
  <customTrackingQueries>
    <customTrackingQuery name="EmailAddress" activityName="SendEmailActivity" />
  </customTrackingQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new CustomTrackingQuery()
          {
              Name = "EmailAddress",
              ActivityName = "SendEmailActivity"
          }
      }
  };
  ```

- <span data-ttu-id="b38bb-166"><xref:System.Activities.Tracking.BookmarkResumptionQuery>: úsela para realizar un seguimiento de la reanudación de un marcador en una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b38bb-166"><xref:System.Activities.Tracking.BookmarkResumptionQuery> - Use this to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="b38bb-167">Esta consulta es necesaria para que <xref:System.Activities.Tracking.TrackingParticipant> se suscriba a los objetos <xref:System.Activities.Tracking.BookmarkResumptionRecord>.</span><span class="sxs-lookup"><span data-stu-id="b38bb-167">This query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.BookmarkResumptionRecord> objects.</span></span>

  <span data-ttu-id="b38bb-168">La configuración y el código que se usen para suscribirse a registros relacionados con la reanudación de marcadores mediante <xref:System.Activities.Tracking.BookmarkResumptionQuery> se muestran en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b38bb-168">The configuration and code used to subscribe to records related to bookmark resumption using <xref:System.Activities.Tracking.BookmarkResumptionQuery> is shown in the following example.</span></span>

  ```xml
  <bookmarkResumptionQueries>
    <bookmarkResumptionQuery name="SentEmailBookmark" />
  </bookmarkResumptionQueries>
  ```

  ```csharp
  TrackingProfile sampleTrackingProfile = new TrackingProfile()
  {
      Name = "Sample Tracking Profile",
      Queries =
      {
          new BookmarkResumptionQuery()
          {
              Name = "sentEmailBookmark"
          }
      }
  };
  ```

### <a name="annotations"></a><span data-ttu-id="b38bb-169">anotaciones</span><span class="sxs-lookup"><span data-stu-id="b38bb-169">Annotations</span></span>

<span data-ttu-id="b38bb-170">Las anotaciones le permiten etiquetar de forma arbitraria registros de seguimiento con un valor que se puede configurar después de la compilación.</span><span class="sxs-lookup"><span data-stu-id="b38bb-170">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="b38bb-171">Por ejemplo, es posible que desee etiquetar varios registros de seguimiento en varios flujos de trabajo con "Servidor de correo" á "Servidor de correo1".</span><span class="sxs-lookup"><span data-stu-id="b38bb-171">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="b38bb-172">De esta forma, se facilita la búsqueda de todos los registros con esta etiqueta cuando se realizan consultas de registros de seguimiento posteriormente.</span><span class="sxs-lookup"><span data-stu-id="b38bb-172">This makes it easy to find all records with this tag when querying tracking records later.</span></span>

<span data-ttu-id="b38bb-173">Para lograr esto, se agrega una anotación a una consulta de seguimiento tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b38bb-173">To accomplish this, an annotation is added to a tracking query as shown in the following example.</span></span>

```xml
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed"/>
  </states>
  <annotations>
    <annotation name="MailServer" value="Mail Server1"/>
  </annotations>
</activityStateQuery>
```

### <a name="how-to-create-a-tracking-profile"></a><span data-ttu-id="b38bb-174">Cómo crear un perfil de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b38bb-174">How to Create a Tracking Profile</span></span>

<span data-ttu-id="b38bb-175">Los elementos de consulta de seguimiento se utilizan [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] para crear un perfil de seguimiento mediante un código o un archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="b38bb-175">Tracking query elements are used to create a tracking profile using either an XML configuration file or [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] code.</span></span> <span data-ttu-id="b38bb-176">A continuación encontrará un ejemplo de un perfil de seguimiento creado mediante un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b38bb-176">Here is an example of a tracking profile created using a configuration file.</span></span>

```xml
<system.serviceModel>
  <tracking>
    <profiles>
      <trackingProfile name="Sample Tracking Profile ">
        <workflow activityDefinitionId="*">
          <!--Specify the tracking profile query elements to subscribe for tracking records-->
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```

> [!WARNING]
> <span data-ttu-id="b38bb-177">Para que WF use el host de servicio de flujo de trabajo, el perfil de seguimiento se crea normalmente con un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b38bb-177">For a WF using the Workflow service host, the tracking profile is typically created using a configuration file.</span></span> <span data-ttu-id="b38bb-178">También es posible crear un perfil de seguimiento con código que use el perfil de seguimiento y la API de consulta de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b38bb-178">It is also possible to create a tracking profile with code using the tracking profile and tracking query API.</span></span>

<span data-ttu-id="b38bb-179">Los perfiles configurados como un archivo de configuración XML se aplican a un participante de seguimiento mediante una extensión de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="b38bb-179">A profile configured as an XML configuration file is applied to a tracking participant using a behavior extension.</span></span> <span data-ttu-id="b38bb-180">Esto se agrega a workflowServiceHost como se describe en la sección posterior Configuración del [seguimiento de un flujo](configuring-tracking-for-a-workflow.md)de trabajo .</span><span class="sxs-lookup"><span data-stu-id="b38bb-180">This is added to a WorkflowServiceHost as described in the later section [Configuring Tracking for a Workflow](configuring-tracking-for-a-workflow.md).</span></span>

<span data-ttu-id="b38bb-181">El nivel de detalle de los registros del seguimiento emitidos por el host está determinado por los valores de configuración en el perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b38bb-181">The verbosity of the tracking records emitted by the host is determined by configuration settings within the tracking profile.</span></span> <span data-ttu-id="b38bb-182">Un participante de seguimiento se suscribe a los registros de seguimiento mediante la adición de consultas a un perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b38bb-182">A tracking participant subscribes to tracking records by adding queries to a tracking profile.</span></span> <span data-ttu-id="b38bb-183">Para suscribirse a todos los registros de seguimiento,\*el perfil de seguimiento debe especificar todas las consultas de seguimiento mediante " " en los campos de nombre de cada una de las consultas.</span><span class="sxs-lookup"><span data-stu-id="b38bb-183">To subscribe to all tracking records, the tracking profile needs to specify all tracking queries using "\*" in the name fields in each of the queries.</span></span>

<span data-ttu-id="b38bb-184">A continuación, se especifican algunos ejemplos comunes de perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b38bb-184">Here are some of the common examples of tracking profiles.</span></span>

- <span data-ttu-id="b38bb-185">Un perfil de seguimiento para obtener registros de instancia del flujo de trabajo y errores.</span><span class="sxs-lookup"><span data-stu-id="b38bb-185">A tracking profile to obtain workflow instance records and faults.</span></span>

  ```xml
  <trackingProfile name="Instance and Fault Records">
    <workflow activityDefinitionId="*">
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="*" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
      <activityStateQueries>
        <activityStateQuery activityName="*">
          <states>
            <state name="Faulted"/>
          </states>
        </activityStateQuery>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
  ```

- <span data-ttu-id="b38bb-186">Un perfil de seguimiento para obtener todos los registros de seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="b38bb-186">A tracking profile to obtain all custom tracking records.</span></span>

  ```xml
  <trackingProfile name="Instance_And_Custom_Records">
    <workflow activityDefinitionId="*">
      <customTrackingQueries>
        <customTrackingQuery name="*" activityName="*" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
  ```

## <a name="see-also"></a><span data-ttu-id="b38bb-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="b38bb-187">See also</span></span>

- [<span data-ttu-id="b38bb-188">Seguimiento de SQL</span><span class="sxs-lookup"><span data-stu-id="b38bb-188">SQL Tracking</span></span>](./samples/sql-tracking.md)
- <span data-ttu-id="b38bb-189">[Supervisión de Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="b38bb-189">[Windows Server App Fabric Monitoring](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="b38bb-190">[Supervisión de aplicaciones con App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="b38bb-190">[Monitoring Applications with App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
