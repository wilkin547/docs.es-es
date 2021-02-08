---
description: 'Más información sobre: instancias de flujo de trabajo no persistentes'
title: Instancias de flujo de trabajo no persistentes
ms.date: 03/30/2017
ms.assetid: 5e01af77-6b14-4964-91a5-7dfd143449c0
ms.openlocfilehash: 0ee5968426a6bb800b9e70ac592c6da191c22511
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787908"
---
# <a name="non-persisted-workflow-instances"></a>Instancias de flujo de trabajo no persistentes

Cuando se crea una nueva instancia de un flujo de trabajo cuyo estado persiste en <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, el host del servicio crea una entrada inicial para ese servicio en el almacén de instancias. Posteriormente, cuando la instancia de flujo de trabajo persiste por primera vez, <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> almacena el estado de la instancia actual. Si el flujo de trabajo se hospeda en el Servicio de activación de procesos de Windows, los datos de implementación del servicio también se escriben en el almacén de la instancia cuando la instancia persiste por primera vez.

Siempre que la instancia de flujo de trabajo no se haya conservado, se encuentra en un estado **no persistente** . Mientras se encuentra en este estado, la instancia de flujo de trabajo no se puede recuperar después de un reciclaje del dominio de aplicación, error del host o error del equipo.

## <a name="the-non-persisted-state"></a>El estado no persistente

Las instancias del flujo de trabajo que no han persistido permanecen en un estado no persistente en los siguientes casos:

- El host del servicio se bloquea antes de que la instancia de flujo de trabajo se guarde por primera vez. La instancia de flujo de trabajo permanece en el almacén de la instancia y no se recupera. Si llega un mensaje correlacionado, la instancia de flujo de trabajo se activa de nuevo.

- La instancia de flujo de trabajo experimenta una excepción antes de ser guardada por primera vez. Dependiendo de lo que devolvió <xref:System.Activities.UnhandledExceptionAction>, se producen los siguientes escenarios:

  - <xref:System.Activities.UnhandledExceptionAction> se establece en <xref:System.Activities.UnhandledExceptionAction.Abort>: cuando se produce una excepción, la información de la implementación del servicio se escribe en el almacén de la instancia y la instancia de flujo de trabajo se descarga desde la memoria. La instancia de flujo de trabajo permanece en un estado no persistente y no se puede recargar.

  - <xref:System.Activities.UnhandledExceptionAction> se establece en <xref:System.Activities.UnhandledExceptionAction.Cancel> o en <xref:System.Activities.UnhandledExceptionAction.Terminate>: cuando se produce una excepción, la información de la implementación del servicio se escribe en el almacén de la instancia y la instancia de actividad se establece en <xref:System.Activities.ActivityInstanceState.Closed>.

Para minimizar el riesgo de encontrar descargadas instancias de flujo de trabajo no persistentes, recomendamos conservar el flujo de trabajo temprano en su ciclo de vida.

## <a name="detection-and-removal-of-non-persisted-instances"></a>Detección y eliminación de instancias no persistentes

<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> no quita cualquier  instancia de flujo de trabajo no persistente del almacén de la instancia. Tampoco quita cualquier propietario de bloqueo caducado que esté asociado con instancias de flujo de trabajo no persistentes.

Recomendamos que el administrador compruebe periódicamente si hay instancias no persistentes en el almacén de instancias. Los administradores pueden quitar esas instancias del almacén de instancias siempre que sepan que este flujo de trabajo no recibirá mensajes correlacionados. Por ejemplo, si la instancia ha estado en la base de datos durante varios meses y sabe que por lo general el flujo de trabajo tiene una duración de varios días, se podría suponer que fue una instancia inicializada que fue bloqueada.

Para encontrar instancias no persistentes en el almacén de instancias de flujo de trabajo de SQL, puede utilizar las siguientes consultas SQL:

- Esta consulta encuentra todas las instancias que no se han conservado y devuelve su identificador y hora de creación (almacenados en hora UTC).

  ```sql
  select InstanceId, CreationTime
      from [System.Activities.DurableInstancing].[Instances]
      where IsInitialized = 0
  ```

- Esta consulta encuentra todas las instancias que no se han conservado, y que no se han cargado, y devuelve su identificador y hora de creación (almacenados en hora UTC).

  ```sql
  select InstanceId, CreationTime
      from [System.Activities.DurableInstancing].[Instances]
      where IsInitialized = 0
          and CurrentMachine is NULL
  ```

- Esta consulta encuentra todas las instancias suspendidas que no se han conservado, y que no se han cargado, y devuelve su identificador y hora de creación (almacenados en hora UTC), el motivo de la suspensión y el nombre de la excepción.

  ```sql
  select InstanceId, CreationTime, SuspensionReason, SuspensionExceptionName
      from [System.Activities.DurableInstancing].[Instances]
      where IsInitialized = 0
          and IsSuspended = 1
  ```

Tenga cuidado al eliminar instancias no persistentes. En general, resulta seguro quitar instancias no persistentes creadas por <xref:System.ServiceModel.Activities.WorkflowServiceHost> que están suspendidas o que no se han cargado. Esas instancias concretas se pueden eliminar del almacén eliminándolas de la vista `[System.Activities.DurableInstancing].[Instances]` mediante el siguiente comando SQL, sustituyendo el identificador de instancia correcto.

```sql
delete [System.Activities.DurableInstancing].[Instances]
    where InstanceId=’078a9bc4-ada5-4f9e-8cce-b0eb0009995f’
```

> [!WARNING]
> No recomendamos quitar todos instancias no persistentes, porque esto incluye instancias que se han creado recientemente y todavía no se han guardado.
