---
title: Seguimiento personalizado
ms.date: 03/30/2017
ms.assetid: 2d191c9f-62f4-4c63-92dd-cda917fcf254
ms.openlocfilehash: 87f72359e16b4268d77148ec16a626c2bac5751c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557037"
---
# <a name="custom-tracking"></a><span data-ttu-id="6e01c-102">Seguimiento personalizado</span><span class="sxs-lookup"><span data-stu-id="6e01c-102">Custom Tracking</span></span>
<span data-ttu-id="6e01c-103">En este ejemplo se muestra cómo crear un participante de seguimiento personalizado y cómo escribir en la consola el contenido de los datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6e01c-103">This sample demonstrates how to create a custom tracking participant and write the contents of the tracking data to console.</span></span> <span data-ttu-id="6e01c-104">Además, el ejemplo muestra cómo emitir objetos <xref:System.Activities.Tracking.CustomTrackingRecord> rellenados con datos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="6e01c-104">In addition, the sample demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects populated with user defined data.</span></span> <span data-ttu-id="6e01c-105">El participante de seguimiento basado en consola filtra los objetos <xref:System.Activities.Tracking.TrackingRecord> que emite el flujo de trabajo utilizando un objeto de perfil de seguimiento creado en código.</span><span class="sxs-lookup"><span data-stu-id="6e01c-105">The console-based tracking participant filters the <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow using a tracking profile object created in code.</span></span>

## <a name="sample-details"></a><span data-ttu-id="6e01c-106">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e01c-106">Sample Details</span></span>
 <span data-ttu-id="6e01c-107">Windows Workflow Foundation (WF) proporciona una infraestructura de seguimiento para realizar un seguimiento de la ejecución de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6e01c-107">Windows Workflow Foundation (WF) provides a tracking infrastructure to track execution of a workflow instance.</span></span> <span data-ttu-id="6e01c-108">El tiempo de ejecución de seguimiento implementa una instancia de flujo de trabajo para emitir eventos relacionados con el ciclo de vida de flujo de trabajo, eventos procedentes de actividades de flujo de trabajo y eventos de seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="6e01c-108">The tracking runtime implements a workflow instance to emit events related to the workflow lifecycle, events from workflow activities and custom tracking events.</span></span> <span data-ttu-id="6e01c-109">En la siguiente tabla se detallan los componentes primarios de la infraestructura de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6e01c-109">The following table details the primary components of the tracking infrastructure.</span></span>

|<span data-ttu-id="6e01c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6e01c-110">Component</span></span>|<span data-ttu-id="6e01c-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e01c-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="6e01c-112">Tiempo de ejecución de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6e01c-112">Tracking runtime</span></span>|<span data-ttu-id="6e01c-113">Proporciona la infraestructura para emitir registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6e01c-113">Provides the infrastructure to emit tracking records.</span></span>|
|<span data-ttu-id="6e01c-114">Participantes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6e01c-114">Tracking participants</span></span>|<span data-ttu-id="6e01c-115">Usa los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6e01c-115">Consumes the tracking records.</span></span> <span data-ttu-id="6e01c-116">.NET Framework 4 incluye un participante de seguimiento que escribe los registros de seguimiento como eventos de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="6e01c-116">.NET Framework 4 ships with a tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span>|
|<span data-ttu-id="6e01c-117">Perfil de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6e01c-117">Tracking profile</span></span>|<span data-ttu-id="6e01c-118">Un mecanismo de filtrado que permite a un participante de seguimiento suscribirse a un subconjunto de los registros de seguimiento emitidos desde una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6e01c-118">A filtering mechanism that allows a tracking participant to subscribe for a subset of the tracking records emitted from a workflow instance.</span></span>|

 <span data-ttu-id="6e01c-119">En la siguiente tabla se detallan los registros de seguimiento que emite el tiempo de ejecución del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6e01c-119">The following table details the tracking records that the workflow runtime emits.</span></span>

|<span data-ttu-id="6e01c-120">Registro de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6e01c-120">Tracking Record</span></span>|<span data-ttu-id="6e01c-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e01c-121">Description</span></span>|
|---------------------|-----------------|
|<span data-ttu-id="6e01c-122">Registros de seguimiento de instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6e01c-122">Workflow instance tracking records.</span></span>|<span data-ttu-id="6e01c-123">Describe el ciclo de vida de la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6e01c-123">Describes the life cycle of the workflow instance.</span></span> <span data-ttu-id="6e01c-124">Por ejemplo, se emite un registro de instancia cuando el flujo de trabajo se inicia o se completa.</span><span class="sxs-lookup"><span data-stu-id="6e01c-124">For example, an instance record is emitted when the workflow starts or completes.</span></span>|
|<span data-ttu-id="6e01c-125">Registros de seguimiento de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="6e01c-125">Activity state Tracking Records.</span></span>|<span data-ttu-id="6e01c-126">Describe la ejecución de la actividad.</span><span class="sxs-lookup"><span data-stu-id="6e01c-126">Details activity execution.</span></span> <span data-ttu-id="6e01c-127">Estos registros indican el estado de una actividad de flujo de trabajo; por ejemplo, cuándo se programa una actividad, cuándo se completa o cuándo se produce un error.</span><span class="sxs-lookup"><span data-stu-id="6e01c-127">These records indicate the state of a workflow activity such as when an activity is scheduled or when the activity completes or when a fault is thrown.</span></span>|
|<span data-ttu-id="6e01c-128">Registro de reanudación de marcadores.</span><span class="sxs-lookup"><span data-stu-id="6e01c-128">Bookmark resumption record.</span></span>|<span data-ttu-id="6e01c-129">Se emite siempre que se reanude un marcador en una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6e01c-129">Emitted whenever a bookmark within a workflow instance is resumed.</span></span>|
|<span data-ttu-id="6e01c-130">Registros de seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="6e01c-130">Custom Tracking Records.</span></span>|<span data-ttu-id="6e01c-131">Un autor del flujo de trabajo puede crear registros de seguimiento personalizados y emitirlos en la actividad personalizada.</span><span class="sxs-lookup"><span data-stu-id="6e01c-131">A workflow author can create Custom Tracking Records and emit them within the custom activity.</span></span>|

 <span data-ttu-id="6e01c-132">El participante de seguimiento se suscribe a un subconjunto de los objetos <xref:System.Activities.Tracking.TrackingRecord> emitidos utilizando perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6e01c-132">The tracking participant subscribes for a subset of the emitted <xref:System.Activities.Tracking.TrackingRecord> objects using tracking profiles.</span></span> <span data-ttu-id="6e01c-133">Un perfil de seguimiento contiene consultas de seguimiento que permiten suscribirse a un tipo de registro de seguimiento concreto.</span><span class="sxs-lookup"><span data-stu-id="6e01c-133">A tracking profile contains tracking queries that allow subscribing for a particular tracking record type.</span></span> <span data-ttu-id="6e01c-134">Los perfiles de seguimiento se pueden especificar mediante código o en la configuración.</span><span class="sxs-lookup"><span data-stu-id="6e01c-134">Tracking profiles can be specified in code or in configuration.</span></span>

### <a name="custom-tracking-participant"></a><span data-ttu-id="6e01c-135">Participante de seguimiento personalizado</span><span class="sxs-lookup"><span data-stu-id="6e01c-135">Custom Tracking Participant</span></span>
 <span data-ttu-id="6e01c-136">La API de participante de seguimiento permite la ampliación del tiempo de ejecución de seguimiento mediante un participante de seguimiento proporcionado por el usuario que puede incluir una lógica personalizada para controlar los objetos <xref:System.Activities.Tracking.TrackingRecord> emitidos por el tiempo de ejecución de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6e01c-136">The tracking participant API allows extension of the tracking runtime with a user provided tracking participant that can include custom logic to handle <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow runtime.</span></span>

 <span data-ttu-id="6e01c-137">Para escribir un participante de seguimiento, el usuario debe implementar <xref:System.Activities.Tracking.TrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="6e01c-137">To write a tracking participant the user must implement <xref:System.Activities.Tracking.TrackingParticipant>.</span></span> <span data-ttu-id="6e01c-138">Concretamente, el participante personalizado debe implementar el método <xref:System.Activities.Tracking.TrackingParticipant.Track%2A>.</span><span class="sxs-lookup"><span data-stu-id="6e01c-138">Specifically, the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method has to be implemented by the custom participant.</span></span> <span data-ttu-id="6e01c-139">Se llama a este método cuando el tiempo de ejecución de flujo de trabajo emite un registro <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="6e01c-139">This method is called when a <xref:System.Activities.Tracking.TrackingRecord> is emitted by the workflow runtime.</span></span>

```csharp
public abstract class TrackingParticipant
{
    protected TrackingParticipant();

    public virtual TrackingProfile TrackingProfile { get; set; }
    public abstract void Track(TrackingRecord record, TimeSpan timeout);
}
```

 <span data-ttu-id="6e01c-140">El participante de seguimiento completo se implementa en el archivo ConsoleTrackingParticipant.cs.</span><span class="sxs-lookup"><span data-stu-id="6e01c-140">The complete tracking participant is implemented in the ConsoleTrackingParticipant.cs file.</span></span> <span data-ttu-id="6e01c-141">El siguiente ejemplo de código es el <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> método para el participante de seguimiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="6e01c-141">The following code example is the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method for the custom tracking participant.</span></span>

```csharp
protected override void Track(TrackingRecord record, TimeSpan timeout)
{
    ...
    WorkflowInstanceRecord workflowInstanceRecord = record as WorkflowInstanceRecord;
    if (workflowInstanceRecord != null)
    {
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " Workflow InstanceID: {0} Workflow instance state: {1}",
            record.InstanceId, workflowInstanceRecord.State));
    }

    ActivityStateRecord activityStateRecord = record as ActivityStateRecord;
    if (activityStateRecord != null)
    {
        IDictionary<String, object> variables = activityStateRecord.Variables;
        StringBuilder vars = new StringBuilder();

        if (variables.Count > 0)
        {
            vars.AppendLine("\n\tVariables:");
            foreach (KeyValuePair<string, object> variable in variables)
            {
                vars.AppendLine(String.Format(
                    "\t\tName: {0} Value: {1}", variable.Key, variable.Value));
            }
        }
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " :Activity DisplayName: {0} :ActivityInstanceState: {1} {2}",
                activityStateRecord.Activity.Name, activityStateRecord.State,
            ((variables.Count > 0) ? vars.ToString() : String.Empty)));
    }

    CustomTrackingRecord customTrackingRecord = record as CustomTrackingRecord;

    if ((customTrackingRecord != null) && (customTrackingRecord.Data.Count > 0))
    {
        ...
    }
    Console.WriteLine();

}
```

 <span data-ttu-id="6e01c-142">El siguiente ejemplo de código agrega el participante de la consola al invocador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6e01c-142">The following code example adds the console participant to the workflow invoker.</span></span>

```csharp
ConsoleTrackingParticipant customTrackingParticipant = new ConsoleTrackingParticipant()
{
    ...
    // The tracking profile is set here, refer to Program.CS
...
}

WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());
invoker.Extensions.Add(customTrackingParticipant);
```

### <a name="emitting-custom-tracking-records"></a><span data-ttu-id="6e01c-143">Emitir registros de seguimiento personalizados</span><span class="sxs-lookup"><span data-stu-id="6e01c-143">Emitting Custom Tracking Records</span></span>
 <span data-ttu-id="6e01c-144">En este ejemplo también se muestra la capacidad de emitir objetos <xref:System.Activities.Tracking.CustomTrackingRecord> desde una actividad de flujo de trabajo personalizada:</span><span class="sxs-lookup"><span data-stu-id="6e01c-144">This sample also demonstrates the ability to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects from a custom workflow activity:</span></span>

- <span data-ttu-id="6e01c-145">Los objetos <xref:System.Activities.Tracking.CustomTrackingRecord> se crean y rellenan con datos definidos por el usuario que se desean emitir con el registro.</span><span class="sxs-lookup"><span data-stu-id="6e01c-145">The <xref:System.Activities.Tracking.CustomTrackingRecord> objects are created and populated with user-defined data that is desired to be emitted with the record.</span></span>

- <span data-ttu-id="6e01c-146"><xref:System.Activities.Tracking.CustomTrackingRecord>Se emite llamando al método Track del <xref:System.Activities.ActivityContext> .</span><span class="sxs-lookup"><span data-stu-id="6e01c-146">The <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted by calling the track method of the <xref:System.Activities.ActivityContext>.</span></span>

 <span data-ttu-id="6e01c-147">En el siguiente ejemplo se muestra cómo emitir objetos <xref:System.Activities.Tracking.CustomTrackingRecord> desde una actividad personalizada.</span><span class="sxs-lookup"><span data-stu-id="6e01c-147">The following example demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects within a custom activity.</span></span>

```csharp
// Create the Custom Tracking Record
CustomTrackingRecord customRecord = new CustomTrackingRecord("OrderIn")
{
    Data =
    {
        {"OrderId", 200},
        {"OrderDate", "20 Aug 2001"}
    }
};

// Emit custom tracking record
context.Track(customRecord);
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="6e01c-148">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e01c-148">To use this sample</span></span>

1. <span data-ttu-id="6e01c-149">Con Visual Studio 2010, abra el archivo de solución CustomTrackingSample. sln.</span><span class="sxs-lookup"><span data-stu-id="6e01c-149">Using Visual Studio 2010, open the CustomTrackingSample.sln solution file.</span></span>

2. <span data-ttu-id="6e01c-150">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="6e01c-150">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="6e01c-151">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="6e01c-151">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e01c-152">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="6e01c-152">The samples may already be installed on your computer.</span></span> <span data-ttu-id="6e01c-153">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6e01c-153">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="6e01c-154">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="6e01c-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6e01c-155">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="6e01c-155">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\CustomTracking`  
  
## <a name="see-also"></a><span data-ttu-id="6e01c-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e01c-156">See also</span></span>

- <span data-ttu-id="6e01c-157">[Ejemplos de supervisión de AppFabric](/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="6e01c-157">[AppFabric Monitoring Samples](/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
