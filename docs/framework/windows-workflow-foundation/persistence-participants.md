---
title: Participantes de persistencia
ms.date: 03/30/2017
ms.assetid: f84d2d5d-1c1b-4f19-be45-65b552d3e9e3
ms.openlocfilehash: 66178adda593192678542ebf5ed8906e0dffc908
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569510"
---
# <a name="persistence-participants"></a>Participantes de persistencia
Un participante de persistencia puede tomar parte en una operación de persistencia (guardar o cargar) desencadenada por un host de la aplicación. El [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] se suministra con dos clases abstractas, **PersistenceParticipant** y **PersistenceIOParticipant**, que puede usar para crear un participante de persistencia. Un participante de persistencia se deriva de una de estas clases, implementa los métodos de interés y, a continuación, agrega una instancia de la clase a la colección <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> del objeto <xref:System.ServiceModel.Activities.WorkflowServiceHost>. El host de la aplicación puede buscar estas extensiones de flujo de trabajo cuando se conserve una instancia de flujo de trabajo e invocar los métodos apropiados en los participantes de persistencia en los momentos adecuados.  
  
 La siguiente lista describe las tareas realizadas por el subsistema de persistencia en distintas fases de la operación de persistencia (guardar). Los participantes de persistencia se usan en la tercera y cuarta fase. Si el participante es un participante de E/S (un participante de persistencia que también participa en operaciones de E/S), también se utiliza el participante en la sexta fase.  
  
1.  Recopila valores integrados, incluso el estado del flujo de trabajo, marcadores, variables asignadas y marca de tiempo.  
  
2.  Recopila todos los participantes de persistencia que se agregaron a la colección de extensiones asociada a la instancia de flujo de trabajo.  
  
3.  Invoca el método <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> implementado por todos los participantes de persistencia.  
  
4.  Invoca el método <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> implementado por todos los participantes de persistencia.  
  
5.  Conserve o guarde el flujo de trabajo en el almacén de persistencia.  
  
6.  Invoca el <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnSave%2A> método en todos los participantes de E/S de persistencia. Si el participante no es un participante de E/S, se omite esta tarea. Si el episodio de persistencia es transaccional, la transacción se proporciona en la propiedad Transaction.Current.  
  
7.  Espera a que se completen todos los participantes de persistencia. Si todos los participantes consiguen almacenar datos de instancia, confirma la transacción.  
  
 Un participante de persistencia se deriva de la **PersistenceParticipant** clase y puede implementar el **CollectValues** y **MapValues** métodos. Un participante de E/S de persistencia se deriva de la **PersistenceIOParticipant** clase y puede implementar el **BeginOnSave** método además de implementar el **CollectValues**y **MapValues** métodos.  
  
 Se completa cada fase antes de que comience la siguiente. Por ejemplo, los valores se recopilan desde **todas** participantes de persistencia en la primera fase. A continuación, se proporcionarán para su asignación todos los valores recopilados en la primera fase a todos los participantes de persistencia en la segunda fase. A continuación, todos los valores recopilados y asignados en la primera y segunda fase se proporcionan al proveedor de persistencia en la tercera fase, etc.  
  
 La siguiente lista describe las tareas realizadas por el subsistema de persistencia en distintas fases de la operación de carga. Los participantes de persistencia se usan en la cuarta fase. Los participantes de E/S de persistencia (participantes de persistencia que también participan en las operaciones de E/S) también se usan en la tercera fase.  
  
1.  Recopila todos los participantes de persistencia que se agregaron a la colección de extensiones asociada a la instancia de flujo de trabajo.  
  
2.  Carga el flujo de trabajo del almacén de persistencia.  
  
3.  Invoca el <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnLoad%2A> en todos los participantes de E/S de persistencia y espera a que todos los participantes de persistencia en completarse. Si el episodio de persistencia es transaccional, la transacción se proporciona en la propiedad Transaction.Current.  
  
4.  Carga la instancia de flujo de trabajo en memoria según los datos recuperados del almacén de persistencia.  
  
5.  Invoca <xref:System.Activities.Persistence.PersistenceParticipant.PublishValues%2A> en cada participante de persistencia.  
  
 Un participante de persistencia se deriva de la **PersistenceParticipant** clase y puede implementar el **PublishValues** método. Un participante de E/S de persistencia se deriva de la **PersistenceIOParticipant** clase y puede implementar el **BeginOnLoad** método además de implementar el **PublishValues**método.  
  
 Al cargar una instancia de flujo de trabajo el proveedor de persistencia crea un bloqueo en esa instancia. Esto evita que más de un host cargue la instancia en un escenario de múltiples nodos. Si intenta cargar una instancia de flujo de trabajo que se ha bloqueado verá una excepción similar al siguiente: La excepción "System.ServiceModel.Persistence.InstanceLockException: No se pudo completar la operación solicitada porque el bloqueo por ejemplo ' 00000000-0000-0000-0000-000000000000' no se pudo adquirir ". Este error se debe a una de las siguientes causas:  
  
-   En un escenario de múltiples nodos, la instancia la carga otro host.  Hay varias maneras diferentes para resolver estos tipos de conflictos: reenviar el procesamiento el nodo que posee el bloqueo y reintentarlo, o forzar la carga, lo que hará que el otro host no pueda guardar el trabajo.  
  
-   En un escenario de un solo nodo y el host está bloqueado.  Cuando el host se inicia de nuevo (un reciclaje de proceso o creando un nuevo generador de proveedores de persistencia), el nuevo host intentar cargar una instancia que ya está bloqueada por el host antiguo porque el bloqueo no ha expirado todavía.  
  
-   En un escenario de un solo nodo y la instancia en cuestión se anuló en algún momento y se creó una nueva instancia del proveedor de persistencia que tiene otro identificador de host.  
  
 El valor de tiempo de espera de bloqueo tiene un valor predeterminado de 5 minutos; puede especificar un valor diferente de tiempo de espera al llamar a <xref:System.ServiceModel.Persistence.PersistenceProvider.Load%2A>.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo: Crear a un participante de persistencia personalizado](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-persistence-participant.md)  
  
## <a name="see-also"></a>Vea también
- [Extensibilidad de almacén](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)
