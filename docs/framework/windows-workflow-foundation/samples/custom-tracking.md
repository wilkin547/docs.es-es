---
title: Seguimiento personalizado
ms.date: 03/30/2017
ms.assetid: 2d191c9f-62f4-4c63-92dd-cda917fcf254
ms.openlocfilehash: 3d125c59196cb2a7d33961e0f271aab8c5663a50
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234576"
---
# <a name="custom-tracking"></a>Seguimiento personalizado

En este ejemplo se muestra cómo crear un participante de seguimiento personalizado y cómo escribir en la consola el contenido de los datos de seguimiento. Además, el ejemplo muestra cómo emitir objetos <xref:System.Activities.Tracking.CustomTrackingRecord> rellenados con datos definidos por el usuario. El participante de seguimiento basado en consola filtra los objetos <xref:System.Activities.Tracking.TrackingRecord> que emite el flujo de trabajo utilizando un objeto de perfil de seguimiento creado en código.

## <a name="sample-details"></a>Detalles del ejemplo

 Windows Workflow Foundation (WF) proporciona una infraestructura de seguimiento para realizar un seguimiento de la ejecución de una instancia de flujo de trabajo. El tiempo de ejecución de seguimiento implementa una instancia de flujo de trabajo para emitir eventos relacionados con el ciclo de vida de flujo de trabajo, eventos procedentes de actividades de flujo de trabajo y eventos de seguimiento personalizados. En la siguiente tabla se detallan los componentes primarios de la infraestructura de seguimiento.

|Componente|Descripción|
|---------------|-----------------|
|Tiempo de ejecución de seguimiento|Proporciona la infraestructura para emitir registros de seguimiento.|
|Participantes de seguimiento|Usa los registros de seguimiento. .NET Framework 4 incluye un participante de seguimiento que escribe los registros de seguimiento como eventos de seguimiento de eventos para Windows (ETW).|
|Perfil de seguimiento|Un mecanismo de filtrado que permite a un participante de seguimiento suscribirse a un subconjunto de los registros de seguimiento emitidos desde una instancia de flujo de trabajo.|

 En la siguiente tabla se detallan los registros de seguimiento que emite el tiempo de ejecución del flujo de trabajo.

|Registro de seguimiento|Descripción|
|---------------------|-----------------|
|Registros de seguimiento de instancia de flujo de trabajo.|Describe el ciclo de vida de la instancia de flujo de trabajo. Por ejemplo, se emite un registro de instancia cuando el flujo de trabajo se inicia o se completa.|
|Registros de seguimiento de estado de actividad.|Describe la ejecución de la actividad. Estos registros indican el estado de una actividad de flujo de trabajo; por ejemplo, cuándo se programa una actividad, cuándo se completa o cuándo se produce un error.|
|Registro de reanudación de marcadores.|Se emite siempre que se reanude un marcador en una instancia de flujo de trabajo.|
|Registros de seguimiento personalizados.|Un autor del flujo de trabajo puede crear registros de seguimiento personalizados y emitirlos en la actividad personalizada.|

 El participante de seguimiento se suscribe a un subconjunto de los objetos <xref:System.Activities.Tracking.TrackingRecord> emitidos utilizando perfiles de seguimiento. Un perfil de seguimiento contiene consultas de seguimiento que permiten suscribirse a un tipo de registro de seguimiento concreto. Los perfiles de seguimiento se pueden especificar mediante código o en la configuración.

### <a name="custom-tracking-participant"></a>Participante de seguimiento personalizado

 La API de participante de seguimiento permite la ampliación del tiempo de ejecución de seguimiento mediante un participante de seguimiento proporcionado por el usuario que puede incluir una lógica personalizada para controlar los objetos <xref:System.Activities.Tracking.TrackingRecord> emitidos por el tiempo de ejecución de flujo de trabajo.

 Para escribir un participante de seguimiento, el usuario debe implementar <xref:System.Activities.Tracking.TrackingParticipant>. Concretamente, el participante personalizado debe implementar el método <xref:System.Activities.Tracking.TrackingParticipant.Track%2A>. Se llama a este método cuando el tiempo de ejecución de flujo de trabajo emite un registro <xref:System.Activities.Tracking.TrackingRecord>.

```csharp
public abstract class TrackingParticipant
{
    protected TrackingParticipant();

    public virtual TrackingProfile TrackingProfile { get; set; }
    public abstract void Track(TrackingRecord record, TimeSpan timeout);
}
```

 El participante de seguimiento completo se implementa en el archivo ConsoleTrackingParticipant.cs. El siguiente ejemplo de código es el <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> método para el participante de seguimiento personalizado.

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

 El siguiente ejemplo de código agrega el participante de la consola al invocador de flujo de trabajo.

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

### <a name="emitting-custom-tracking-records"></a>Emitir registros de seguimiento personalizados

 En este ejemplo también se muestra la capacidad de emitir objetos <xref:System.Activities.Tracking.CustomTrackingRecord> desde una actividad de flujo de trabajo personalizada:

- Los objetos <xref:System.Activities.Tracking.CustomTrackingRecord> se crean y rellenan con datos definidos por el usuario que se desean emitir con el registro.

- <xref:System.Activities.Tracking.CustomTrackingRecord>Se emite llamando al método Track del <xref:System.Activities.ActivityContext> .

 En el siguiente ejemplo se muestra cómo emitir objetos <xref:System.Activities.Tracking.CustomTrackingRecord> desde una actividad personalizada.

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

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Con Visual Studio 2010, abra el archivo de solución CustomTrackingSample. sln.

2. Para compilar la solución, presione Ctrl+MAYÚS+B.

3. Para ejecutar la solución, presione CTRL+F5.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\CustomTracking`  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de supervisión de AppFabric](/previous-versions/appfabric/ff383407(v=azure.10))
