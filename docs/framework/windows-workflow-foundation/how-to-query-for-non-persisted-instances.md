---
title: Procedimiento para consultar instancias no guardadas
ms.date: 03/30/2017
ms.assetid: 294019b1-c1a7-4b81-a14f-b47c106cd723
ms.openlocfilehash: 54a442dab6700dda33cf05df1fb5c60a96bcbd56
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280005"
---
# <a name="how-to-query-for-non-persisted-instances"></a>Procedimiento para consultar instancias no guardadas

Cuando se crea una nueva instancia de un servicio y este tiene el comportamiento del almacén de instancias de flujo de trabajo de SQL definido, el host del servicio crea una entrada inicial para esa instancia en el almacén de instancias. Como consecuencia, cuando la instancia de servicio se guarda por primera vez, el comportamiento del almacén de instancias de flujo de trabajo de SQL almacena el estado de la instancia actual junto con los datos adicionales que se requieren para la activación, recuperación y control.

Si una instancia no se guarda después de crear la entrada inicial para la instancia, se dice que la instancia de servicio está en el estado no conservado. Todas las instancias de servicio conservadas pueden consultar y controlar. Las instancias de servicio no conservadas no se pueden consultar ni controlar. Si una instancia no conservada se suspende debido a una excepción no controlada, se puede consultar pero no controlar.

Las instancias de servicio duraderas que todavía no se han guardado permanecen en un estado no conservado en los siguientes casos:

- El host del servicio se bloquea antes de que la instancia se guarde por primera vez. La entrada inicial para la instancia permanece en el almacén de instancias. La instancia no se puede recuperar. Si lleva un mensaje correlacionado, la instancia pasa a estar de nuevo activa.

- La instancia experimenta una excepción no controlada antes de ser guardada por primera vez. Se producen los siguientes escenarios:

  - Si el valor de la propiedad **UnhandledExceptionAction** se establece en **Abandon**, la información de implementación del servicio se escribe en el almacén de instancias y la instancia se descarga de la memoria. La instancia permanece en un estado no conservado en la base de datos de persistencia.

  - Si el valor de la propiedad **UnhandledExceptionAction** se establece en **AbandonAndSuspend**, la información de implementación del servicio se escribe en la base de datos de persistencia y el estado de la instancia se establece en **Suspended**. La instancia no se puede reanudar, cancelar ni finalizar. El host del servicio no puede cargar la instancia porque esta todavía no se ha guardado y, por lo tanto, la entrada de base de datos para la instancia no está completa.

  - Si el valor de la propiedad **UnhandledExceptionAction** está establecido en **Cancelar** o **Finalizar**, la información de implementación del servicio se escribe en el almacén de instancias y el estado de la instancia se establece en **completado**.

En las siguientes secciones se proporcionan consultas de ejemplo para localizar instancias no conservadas en la base de datos de persistencia de SQL y para eliminar estas instancias de la base de datos.

## <a name="to-find-all-instances-not-persisted-yet"></a>Para localizar todas las instancias que todavía no se han guardado

La siguiente consulta SQL devuelve el identificador y la hora de creación de todas las instancias que todavía no se han guardado en la base de datos de persistencia.

```sql
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0;
```

## <a name="to-find-all-instances-not-persisted-yet-and-also-not-loaded"></a>Para localizar todas las instancias que todavía y no se han guardado ni cargado

 La siguiente consulta SQL devuelve el identificador y la hora de creación de todas las instancias que no se han guardado ni tampoco cargado.

```sql
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and CurrentMachine is NULL;
```

## <a name="to-find-all-suspended-instances-not-persisted-yet"></a>Para localizar todas las instancias suspendidas que todavía no se han guardado

La siguiente consulta SQL devuelve el identificador, la hora de creación, el motivo de la suspensión y el nombre de excepción de la suspensión de todas las instancias que no se han guardado y están en estado suspendido.

```sql
select InstanceId, CreationTime, SuspensionReason, SuspensionExceptionName from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and IsSuspended = 1;
```

## <a name="to-delete-non-persisted-instances-from-the-persistence-database"></a>Para eliminar las instancias no conservadas de la base de datos de persistencia

Debe comprobar periódicamente en el almacén de instancias la existencia de instancias no conservadas y quitarlas si está seguro de que la instancia no recibirá ningún mensaje correlacionado. Por ejemplo, si la instancia ha estado en la base de datos durante varios meses y sabe que por lo general el flujo de trabajo tiene una duración de unos días, se podría suponer que se trata de una instancia no inicializada que se ha bloqueado.

En general, resulta seguro eliminar instancias no conservadas que no están suspendidas ni se han cargado. No debe eliminar **todas** las instancias no persistentes porque este conjunto de instancias incluye instancias que se acaban de crear pero que todavía no se han guardado. Solamente debe eliminar las instancias no conservadas que quedan porque se produjo una excepción en el host del servicio de flujo de trabajo que tenía la instancia cargada o porque se produjo una excepción en la propia instancia.

> [!WARNING]
> La eliminación de instancias no conservadas del almacén de instancias reduce el tamaño del almacén y puede mejorar el rendimiento de las operaciones del almacén.
