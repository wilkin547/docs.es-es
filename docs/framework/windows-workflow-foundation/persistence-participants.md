---
title: Participantes de persistencia
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f84d2d5d-1c1b-4f19-be45-65b552d3e9e3
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bc2a6da9a43e29091c4ff9d086e9259594a01718
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="persistence-participants"></a>Participantes de persistencia
Un participante de persistencia puede tomar parte en una operación de persistencia (guardar o cargar) desencadenada por un host de la aplicación. El [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] se distribuye con dos clases abstractas, **PersistenceParticipant** y **PersistenceIOParticipant**, que puede usar para crear un participante de persistencia. Un participante de persistencia se deriva de una de estas clases, implementa los métodos de interés y, a continuación, agrega una instancia de la clase a la colección <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> del objeto <xref:System.ServiceModel.Activities.WorkflowServiceHost>. El host de la aplicación puede buscar estas extensiones de flujo de trabajo cuando se conserve una instancia de flujo de trabajo e invocar los métodos apropiados en los participantes de persistencia en los momentos adecuados.  
  
 La siguiente lista describe las tareas realizadas por el subsistema de persistencia en distintas fases de la operación de persistencia (guardar). Los participantes de persistencia se usan en la tercera y cuarta fase. Si el participante es un participante de E/S (un participante de persistencia que también toma parte en operaciones de E/S), también se usa en la sexta fase.  
  
1.  Recopila valores integrados, incluso el estado del flujo de trabajo, marcadores, variables asignadas y marca de tiempo.  
  
2.  Recopila todos los participantes de persistencia que se agregaron a la colección de extensiones asociada a la instancia de flujo de trabajo.  
  
3.  Invoca el método <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> implementado por todos los participantes de persistencia.  
  
4.  Invoca el método <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> implementado por todos los participantes de persistencia.  
  
5.  Conserve o guarde el flujo de trabajo en el almacén de persistencia.  
  
6.  Invoca el método <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnSave%2A> en todos los participantes de E/S de persistencia. Si el participante no es un participante de E/S, se omite esta tarea. Si el episodio de persistencia es transaccional, la transacción se proporciona en la propiedad Transaction.Current.  
  
7.  Espera a que se completen todos los participantes de persistencia. Si todos los participantes consiguen almacenar datos de instancia, confirma la transacción.  
  
 Un participante de persistencia deriva de la **PersistenceParticipant** clase y puede implementar la **CollectValues** y **MapValues** métodos. Un participante de E/S de persistencia deriva de la **PersistenceIOParticipant** clase y puede implementar la **BeginOnSave** método además de implementar la **CollectValues**y **MapValues** métodos.  
  
 Se completa cada fase antes de que comience la siguiente. Por ejemplo, los valores se recopilan de **todos los** participantes de persistencia en la primera fase. A continuación, se proporcionarán para su asignación todos los valores recopilados en la primera fase a todos los participantes de persistencia en la segunda fase. A continuación, todos los valores recopilados y asignados en la primera y segunda fase se proporcionan al proveedor de persistencia en la tercera fase, etc.  
  
 La siguiente lista describe las tareas realizadas por el subsistema de persistencia en distintas fases de la operación de carga. Los participantes de persistencia se usan en la cuarta fase. También se usan participantes de E/S de persistencia (participantes de persistencia que también participan en operaciones de E/S) en la tercera fase.  
  
1.  Recopila todos los participantes de persistencia que se agregaron a la colección de extensiones asociada a la instancia de flujo de trabajo.  
  
2.  Carga el flujo de trabajo del almacén de persistencia.  
  
3.  Invoca <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnLoad%2A> en todos los participantes de E/S de persistencia y espera a que se completen todos los participantes de persistencia. Si el episodio de persistencia es transaccional, la transacción se proporciona en la propiedad Transaction.Current.  
  
4.  Carga la instancia de flujo de trabajo en memoria según los datos recuperados del almacén de persistencia.  
  
5.  Invoca <xref:System.Activities.Persistence.PersistenceParticipant.PublishValues%2A> en cada participante de persistencia.  
  
 Un participante de persistencia deriva de la **PersistenceParticipant** clase y puede implementar la **PublishValues** método. Un participante de E/S de persistencia deriva de la **PersistenceIOParticipant** clase y puede implementar la **BeginOnLoad** método además de implementar la **PublishValues**(método).  
  
 Al cargar una instancia de flujo de trabajo el proveedor de persistencia crea un bloqueo en esa instancia. Esto evita que más de un host cargue la instancia en un escenario de múltiples nodos. Si intenta cargar una instancia de flujo de trabajo que ha estado bloqueada verá una excepción similar al siguiente: la excepción "System.ServiceModel.Persistence.InstanceLockException: no se pudo completar la operación solicitada porque el bloqueo para la instancia ' 00000000-0000-0000-0000-000000000000' no se pudo adquirir ". Este error se debe a una de las siguientes causas:  
  
-   En un escenario de múltiples nodos, la instancia la carga otro host.  Hay varias maneras diferentes para resolver estos tipos de conflictos: reenviar el procesamiento el nodo que posee el bloqueo y reintentarlo, o forzar la carga, lo que hará que el otro host no pueda guardar el trabajo.  
  
-   En un escenario de un solo nodo y el host está bloqueado.  Cuando el host se inicia de nuevo (un reciclaje de proceso o creando un nuevo generador de proveedores de persistencia), el nuevo host intentar cargar una instancia que ya está bloqueada por el host antiguo porque el bloqueo no ha expirado todavía.  
  
-   En un escenario de un solo nodo y la instancia en cuestión se anuló en algún momento y se creó una nueva instancia del proveedor de persistencia que tiene otro identificador de host.  
  
 El valor de tiempo de espera de bloqueo tiene un valor predeterminado de 5 minutos; puede especificar un valor diferente de tiempo de espera al llamar a <xref:System.ServiceModel.Persistence.PersistenceProvider.Load%2A>.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo crear un participante de persistencia personalizado](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-persistence-participant.md)  
  
## <a name="see-also"></a>Vea también  
 [Extensibilidad de almacén](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)
