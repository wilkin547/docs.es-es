---
title: Participantes de persistencia
ms.date: 03/30/2017
ms.assetid: f84d2d5d-1c1b-4f19-be45-65b552d3e9e3
ms.openlocfilehash: 0bff6cc8fafb1832dc4d0e33b754fe3adb81dcf6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246113"
---
# <a name="persistence-participants"></a>Participantes de persistencia

Un participante de persistencia puede tomar parte en una operación de persistencia (guardar o cargar) desencadenada por un host de la aplicación. [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]Se distribuye con dos clases abstractas, **PersistenceParticipant** y **PersistenceIOParticipant**, que puede usar para crear un participante de persistencia. Un participante de persistencia se deriva de una de estas clases, implementa los métodos de interés y, a continuación, agrega una instancia de la clase a la colección <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> del objeto <xref:System.ServiceModel.Activities.WorkflowServiceHost>. El host de la aplicación puede buscar estas extensiones de flujo de trabajo cuando se conserve una instancia de flujo de trabajo e invocar los métodos apropiados en los participantes de persistencia en los momentos adecuados.  
  
 La siguiente lista describe las tareas realizadas por el subsistema de persistencia en distintas fases de la operación de persistencia (guardar). Los participantes de persistencia se usan en la tercera y cuarta fase. Si el participante es un participante de e/s (un participante de persistencia que también participa en operaciones de e/s), el participante también se usa en la sexta fase.  
  
1. Recopila valores integrados, incluso el estado del flujo de trabajo, marcadores, variables asignadas y marca de tiempo.  
  
2. Recopila todos los participantes de persistencia que se agregaron a la colección de extensiones asociada a la instancia de flujo de trabajo.  
  
3. Invoca el método <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> implementado por todos los participantes de persistencia.  
  
4. Invoca el método <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> implementado por todos los participantes de persistencia.  
  
5. Conserve o guarde el flujo de trabajo en el almacén de persistencia.  
  
6. Invoca el <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnSave%2A> método en todos los participantes de e/s de persistencia. Si el participante no es un participante de e/s, se omitirá esta tarea. Si el episodio de persistencia es transaccional, la transacción se proporciona en la propiedad Transaction.Current.  
  
7. Espera a que se completen todos los participantes de persistencia. Si todos los participantes consiguen almacenar datos de instancia, confirma la transacción.  
  
 Un participante de persistencia deriva de la clase **PersistenceParticipant** y puede implementar los métodos **CollectValues** y **MapValues** . Un participante de e/s de persistencia deriva de la clase **PersistenceIOParticipant** y puede implementar el método **método beginonsave** además de implementar los métodos **CollectValues** y **MapValues** .  
  
 Se completa cada fase antes de que comience la siguiente. Por ejemplo, los valores se recopilan de **todos los** participantes de persistencia en la primera fase. A continuación, se proporcionarán para su asignación todos los valores recopilados en la primera fase a todos los participantes de persistencia en la segunda fase. A continuación, todos los valores recopilados y asignados en la primera y segunda fase se proporcionan al proveedor de persistencia en la tercera fase, etc.  
  
 La siguiente lista describe las tareas realizadas por el subsistema de persistencia en distintas fases de la operación de carga. Los participantes de persistencia se usan en la cuarta fase. Los participantes de e/s de persistencia (participantes de persistencia que también participan en operaciones de e/s) también se usan en la tercera fase.  
  
1. Recopila todos los participantes de persistencia que se agregaron a la colección de extensiones asociada a la instancia de flujo de trabajo.  
  
2. Carga el flujo de trabajo del almacén de persistencia.  
  
3. Invoca <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnLoad%2A> en todos los participantes de e/s de persistencia y espera a que se completen todos los participantes de persistencia. Si el episodio de persistencia es transaccional, la transacción se proporciona en la propiedad Transaction.Current.  
  
4. Carga la instancia de flujo de trabajo en memoria según los datos recuperados del almacén de persistencia.  
  
5. Invoca <xref:System.Activities.Persistence.PersistenceParticipant.PublishValues%2A> en cada participante de persistencia.  
  
 Un participante de persistencia deriva de la clase **PersistenceParticipant** y puede implementar el método **PublishValues** . Un participante de e/s de persistencia deriva de la clase **PersistenceIOParticipant** y puede implementar el método **BeginOnLoad** además de implementar el método **PublishValues** .  
  
 Al cargar una instancia de flujo de trabajo el proveedor de persistencia crea un bloqueo en esa instancia. Esto evita que más de un host cargue la instancia en un escenario de múltiples nodos. Si intenta cargar una instancia de flujo de trabajo que ha estado bloqueada verá una excepción como la siguiente: Excepción "System.ServiceModel.Persistence.InstanceLockException: La operación solicitada no se pudo completar porque no fue posible realizar el bloqueo de la instancia '00000000-0000-0000-0000-000000000000'". Este error se debe a una de las siguientes causas:  
  
- En un escenario de múltiples nodos, la instancia la carga otro host.  Hay varias maneras diferentes para resolver estos tipos de conflictos: reenviar el procesamiento el nodo que posee el bloqueo y reintentarlo, o forzar la carga, lo que hará que el otro host no pueda guardar el trabajo.  
  
- En un escenario de un solo nodo y el host está bloqueado.  Cuando el host se inicia de nuevo (un reciclaje de proceso o creando un nuevo generador de proveedores de persistencia), el nuevo host intentar cargar una instancia que ya está bloqueada por el host antiguo porque el bloqueo no ha expirado todavía.  
  
- En un escenario de un solo nodo y la instancia en cuestión se anuló en algún momento y se creó una nueva instancia del proveedor de persistencia que tiene otro identificador de host.  
  
 El valor de tiempo de espera de bloqueo tiene un valor predeterminado de 5 minutos; puede especificar un valor diferente de tiempo de espera al llamar a <xref:System.ServiceModel.Persistence.PersistenceProvider.Load%2A>.  
  
## <a name="in-this-section"></a>En esta sección  
  
- [Procedimiento para crear un participante de persistencia personalizado](how-to-create-a-custom-persistence-participant.md)  
  
## <a name="see-also"></a>Vea también

- [Extensibilidad de almacén](store-extensibility.md)
