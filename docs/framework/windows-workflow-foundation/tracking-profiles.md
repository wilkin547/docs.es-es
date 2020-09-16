---
title: Perfiles de seguimiento
ms.date: 03/30/2017
ms.assetid: 22682566-1cd9-4672-9791-fb3523638e18
ms.openlocfilehash: ceeb0f5533bb4c637ea7df52249f5b00067d9b3d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551392"
---
# <a name="tracking-profiles"></a>Perfiles de seguimiento

Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.

## <a name="tracking-profiles"></a>Perfiles de seguimiento

Los perfiles de seguimiento se usan para especificar qué información de seguimiento se emite para una instancia de flujo de trabajo. Si no se especifica ningún perfil, se emiten todos los eventos de seguimiento. Si se especifica un perfil, se emitirán los eventos de seguimiento especificados en el perfil. Dependiendo de sus requisitos de supervisión, puede escribir un perfil que es muy general, que se suscribe a un conjunto pequeño de cambios de estado de alto nivel en un flujo de trabajo. En cambio, puede crear un perfil muy detallado cuyos eventos resultantes estén lo suficientemente enriquecidos para reconstruir un flujo de ejecución detallado más adelante.

Los perfiles de seguimiento se manifiestan como elementos XML dentro de un archivo de configuración de .NET Framework estándar o se especifican en el código. El siguiente ejemplo es de un perfil de seguimiento de [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] en un archivo de configuración que permite a un participante de seguimiento suscribirse a los eventos de flujo de trabajo `Started` y `Completed`.

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

El ejemplo siguiente muestra el perfil de seguimiento equivalente creado mediante código.

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

Los registros de seguimiento se filtran a través del modo de visibilidad dentro de un perfil de seguimiento mediante el atributo <xref:System.Activities.Tracking.ImplementationVisibility>. Una actividad compuesta es una actividad de nivel superior que contiene otras actividades que forman su implementación. El modo de visibilidad especifica los registros de seguimiento emitidos desde actividades compuestas dentro de una actividad de flujo de trabajo para especificar si se realiza el seguimiento de las actividades que forman la implementación. El modo de visibilidad se aplica en el nivel del perfil de seguimiento. Las consultas incluidas en el perfil de seguimiento controlan el filtrado de los registros de seguimiento para las actividades individuales dentro de un flujo de trabajo. Para obtener más información, consulte la sección **tipos de consulta de Perfil de seguimiento** en este documento.

Los dos modos de visibilidad especificados por el atributo `implementationVisibility` en el perfil de seguimiento son `RootScope` y `All`. Al usar el modo `RootScope`, se suprimen los registros de seguimiento para las actividades que forman la implementación de una actividad en el caso de que una actividad compuesta no sea la raíz de un flujo de trabajo. Esto implica que, cuando una actividad que se implementa usando otras actividades se agrega a un flujo de trabajo y `implementationVisibility` está definido en RootScope, sólo se realiza el seguimiento de la actividad de nivel superior incluida en esa actividad compuesta. Si una actividad es la raíz del flujo de trabajo, la implementación de la actividad es el propio flujo de trabajo y los registros de seguimiento se emiten para actividades que forman la implementación. Gracias al modo All, se permite que todos los registros de seguimiento se emitan para la actividad raíz y todas sus actividades compuestas.

Por ejemplo, supongamos que mi *actividad* es una actividad compuesta cuya implementación contiene dos actividades, *Activity1* y *Activity2*. Cuando esta actividad se agrega a un flujo de trabajo y el seguimiento está habilitado con un perfil de seguimiento con `implementationVisibility` establecido en `RootScope` , los registros de seguimiento solo se emiten para la *actividad*. Sin embargo, no se emiten registros para las actividades *Activity1* y *Activity2*.

Sin embargo, si el `implementationVisibility` atributo para el perfil de seguimiento está establecido en `All` , los registros de seguimiento se emiten no solo para la *actividad*, sino también para las actividades *Activity1* y *Activity2*.

La marca `implementationVisibility` se aplica a los siguientes tipos de registro de seguimiento:

- ActivityStateRecord

- FaultPropagationRecord

- CancelRequestedRecord

- ActivityScheduledRecord

> [!NOTE]
> CustomTrackingRecords emitidos a partir de la implementación de actividad no se filtran por el valor implementationVisibility.

La funcionalidad `implementationVisibility` se especifica como <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> en el perfil de seguimiento en código de la siguiente forma:

```csharp
TrackingProfile sampleTrackingProfile = new TrackingProfile()
{
    Name = "Sample Tracking Profile",
    ImplementationVisibility = ImplementationVisibility.RootScope
};
```

La funcionalidad `implementationVisibility` se especifica como <xref:System.Activities.Tracking.ImplementationVisibility.All> en el perfil de seguimiento en un archivo de configuración de la siguiente manera:

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

El valor `ImplementationVisibility` en el perfil de seguimiento es opcional. De manera predeterminada, su valor está definido en `RootScope`. Los valores para este atributo distinguen entre mayúsculas y minúsculas.

### <a name="tracking-profile-query-types"></a>Tipos de consulta de perfil de seguimiento

Los perfiles de seguimiento se estructuran como suscripciones declarativas para los registros de seguimiento que le permiten consultar el tiempo de ejecución de flujo de trabajo para registros de seguimiento específicos. Hay varios tipos de consulta que permiten que se suscriba a clases diferentes de objetos <xref:System.Activities.Tracking.TrackingRecord>. Los perfiles de seguimiento se pueden especificar en la configuración o a través del código. A continuación, se describen los tipos de consulta más comunes:

- <xref:System.Activities.Tracking.WorkflowInstanceQuery>: úsela para realizar el seguimiento de los cambios de ciclo de vida de la instancia de flujo de trabajo como los valores `Started` y `Completed` mostrados previamente. <xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:

  - <xref:System.Activities.Tracking.WorkflowInstanceRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>

  - <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>

  Los estados a los que se puede suscribir se especifican en la clase <xref:System.Activities.Tracking.WorkflowInstanceStates>.

  La configuración o código usados para suscribirse a los registros de seguimiento en el nivel de instancia del flujo de trabajo correspondientes al estado de la instancia `Started` que usa <xref:System.Activities.Tracking.WorkflowInstanceQuery> se muestran en el siguiente ejemplo.

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

- <xref:System.Activities.Tracking.ActivityStateQuery>: úsela para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo. Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo. Esta consulta es necesaria para que <xref:System.Activities.Tracking.TrackingParticipant> se suscriba a los objetos <xref:System.Activities.Tracking.ActivityStateRecord>. Los estados de suscripción disponibles se especifican en <xref:System.Activities.Tracking.ActivityStates>.

  La configuración y el código usados para suscribirse a los registros de seguimiento del estado de la actividad que usan <xref:System.Activities.Tracking.ActivityStateQuery> para la actividad `SendEmailActivity` se muestran en el siguiente ejemplo.

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
  > Si hay varios elementos activityStateQuery con el mismo nombre, solo se los estados del último elemento en el perfil de seguimiento.

- <xref:System.Activities.Tracking.ActivityScheduledQuery>: esta consulta le permite realizar el seguimiento de una actividad programada para que sea ejecutada por una actividad primaria. La consulta es necesaria para que <xref:System.Activities.Tracking.TrackingParticipant> se suscriba a los objetos <xref:System.Activities.Tracking.ActivityScheduledRecord>.

  La configuración y el código usados para suscribirse a los registros relacionados con la actividad secundaria `SendEmailActivity` que se está programando con <xref:System.Activities.Tracking.ActivityScheduledQuery> se muestran en el siguiente ejemplo.

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

- <xref:System.Activities.Tracking.FaultPropagationQuery>: use este valor para realizar el seguimiento del control de errores que se producen dentro de una actividad. La consulta es necesaria para que <xref:System.Activities.Tracking.TrackingParticipant> se suscriba a los objetos <xref:System.Activities.Tracking.FaultPropagationRecord>.

  La configuración y el código que se usen para suscribirse a registros relacionados con la propagación de errores mediante <xref:System.Activities.Tracking.FaultPropagationQuery> se muestran en el ejemplo siguiente.

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

- <xref:System.Activities.Tracking.CancelRequestedQuery>: úsela para realizar un seguimiento de las solicitudes para cancelar una actividad secuncaria mediante la actividad primaria. La consulta es necesaria para que <xref:System.Activities.Tracking.TrackingParticipant> se suscriba a los objetos <xref:System.Activities.Tracking.CancelRequestedRecord>.

  La configuración y el código usados para suscribirse a registros relacionados con la cancelación de la actividad mediante <xref:System.Activities.Tracking.CancelRequestedQuery> se muestran en el ejemplo siguiente.

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

- <xref:System.Activities.Tracking.CustomTrackingQuery>: úsela para realizar el seguimiento de eventos que defina en las actividades de código. La consulta es necesaria para que <xref:System.Activities.Tracking.TrackingParticipant> se suscriba a los objetos <xref:System.Activities.Tracking.CustomTrackingRecord>.

  La configuración y el código usados para suscribirse a los registros relacionados con los registros de seguimiento personalizados mediante <xref:System.Activities.Tracking.CustomTrackingQuery> se muestran en el siguiente ejemplo.

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

- <xref:System.Activities.Tracking.BookmarkResumptionQuery>: úsela para realizar un seguimiento de la reanudación de un marcador en una instancia de flujo de trabajo. Esta consulta es necesaria para que <xref:System.Activities.Tracking.TrackingParticipant> se suscriba a los objetos <xref:System.Activities.Tracking.BookmarkResumptionRecord>.

  La configuración y el código que se usen para suscribirse a registros relacionados con la reanudación de marcadores mediante <xref:System.Activities.Tracking.BookmarkResumptionQuery> se muestran en el ejemplo siguiente.

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

### <a name="annotations"></a>anotaciones

Las anotaciones le permiten etiquetar de forma arbitraria registros de seguimiento con un valor que se puede configurar después de la compilación. Por ejemplo, puede que desee etiquetar varios registros de seguimiento en varios flujos de trabajo con "servidor de correo" = = "mail server1". De esta forma, se facilita la búsqueda de todos los registros con esta etiqueta cuando se realizan consultas de registros de seguimiento posteriormente.

Para lograr esto, se agrega una anotación a una consulta de seguimiento tal y como se muestra en el siguiente ejemplo.

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

### <a name="how-to-create-a-tracking-profile"></a>Cómo crear un perfil de seguimiento

Los elementos de consulta de seguimiento se usan para crear un perfil de seguimiento mediante un archivo de configuración XML o [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] código. A continuación encontrará un ejemplo de un perfil de seguimiento creado mediante un archivo de configuración.

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
> Para que WF use el host de servicio de flujo de trabajo, el perfil de seguimiento se crea normalmente con un archivo de configuración. También es posible crear un perfil de seguimiento con código que use el perfil de seguimiento y la API de consulta de seguimiento.

Los perfiles configurados como un archivo de configuración XML se aplican a un participante de seguimiento mediante una extensión de comportamiento. Esto se agrega a WorkflowServiceHost tal y como se describe en la sección posterior [configurar el seguimiento de un flujo de trabajo](configuring-tracking-for-a-workflow.md).

El nivel de detalle de los registros del seguimiento emitidos por el host está determinado por los valores de configuración en el perfil de seguimiento. Un participante de seguimiento se suscribe a los registros de seguimiento mediante la adición de consultas a un perfil de seguimiento. Para suscribirse a todos los registros de seguimiento, el perfil de seguimiento debe especificar todas las consultas de seguimiento mediante " \* " en los campos de nombre de cada una de las consultas.

A continuación, se especifican algunos ejemplos comunes de perfiles de seguimiento.

- Un perfil de seguimiento para obtener registros de instancia del flujo de trabajo y errores.

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

- Un perfil de seguimiento para obtener todos los registros de seguimiento personalizados.

  ```xml
  <trackingProfile name="Instance_And_Custom_Records">
    <workflow activityDefinitionId="*">
      <customTrackingQueries>
        <customTrackingQuery name="*" activityName="*" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
  ```

## <a name="see-also"></a>Vea también

- [Seguimiento de SQL](./samples/sql-tracking.md)
- [Supervisión de Windows Server App fabric](/previous-versions/appfabric/ee677251(v=azure.10))
- [Supervisión de aplicaciones con App fabric](/previous-versions/appfabric/ee677276(v=azure.10))
