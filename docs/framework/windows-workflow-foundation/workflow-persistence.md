---
title: Persistencia del flujo de trabajo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- programming [WF], persistence
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9e65f07fc01d0d364d7271c4f1378b968b687881
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-persistence"></a>Persistencia del flujo de trabajo
La persistencia del flujo de trabajo es la captura duradera de un estado de la instancia de flujo de trabajo, independientemente de la información del proceso o del equipo. Esto sirve para proporcionar un punto de recuperación conocido para la instancia de flujo de trabajo en caso de error del sistema, para conservar la memoria descargando instancias de flujo de trabajo que no están funcionando de forma activa o para mover el estado de la instancia de flujo de trabajo de un nodo a otro en una granja de servidores.  
  
 La persistencia permite procesar la agilidad, escalabilidad, recuperación en caso de error y la capacidad de administrar la memoria más eficazmente. El proceso de persistencia incluye la identificación de un punto de persistencia, la recopilación de los datos que se van a guardar y finalmente la delegación del almacenamiento real de los datos a un proveedor de persistencia.  
  
 Para habilitar la persistencia para un flujo de trabajo, debe asociar un almacén de instancias con el **WorkflowApplication** o **WorkflowServiceHost** como se mencionó en [Cómo: habilitar la persistencia para Los flujos de trabajo y los servicios de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md). El **WorkflowApplication** y **WorkflowServiceHost** usar el almacén de instancia asociado a ellos para habilitar la persistencia de instancias de flujo de trabajo en un almacén de persistencia y cargar instancias de flujo de trabajo en memoria en función de los datos de instancia de flujo de trabajo almacenados en el almacén de persistencia.  
  
 El [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] se suministra con la **SqlWorkflowInstanceStore** (clase), que permite la persistencia de datos y metadatos acerca de las instancias de flujo de trabajo en una base de datos de SQL Server 2005 o SQL Server 2008. Vea [almacén de instancias de flujo de trabajo de SQL](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) para obtener más detalles.  
  
 Para almacenar y cargar los datos específicos de la aplicación junto con la información relacionada con la instancia de flujo de trabajo, puede crear participantes de persistencia que extienden la clase <xref:System.Activities.Persistence.PersistenceParticipant>. Los participantes de persistencia participan en el proceso de persistencia para guardar los datos serializables personalizados en el almacén de persistencia, para cargar los datos del almacén de instancias en la memoria y para realizar cualquier lógica adicional en una transacción de persistencia. Para obtener más información, consulte [participantes de persistencia](../../../docs/framework/windows-workflow-foundation/persistence-participants.md).  
  
 Windows Server APp Fabric simplifica el proceso de configuración de persistencia. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Conceptos de persistencia con Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201200)  
  
## <a name="implicit-persistence-points"></a>Puntos de persistencia implícitos  
 La siguiente lista contiene ejemplos de las condiciones en las que se conserva un flujo de trabajo cuando se asocia un almacén de instancias a este.  
  
-   Cuando un **TransactionScope** actividad se completa o una **TransactedReceiveScope** completa de la actividad.  
  
-   Cuando una instancia de flujo de trabajo se vuelve inactiva y el **WorkflowIdleBehavior** se establece en el host de flujo de trabajo. Esto ocurre, por ejemplo, cuando use las actividades de mensajería o un **retraso** actividad.  
  
-   Cuando WorkflowApplication se vuelve inactiva y el **PersistableIdle** propiedad de la aplicación está establecida en **PersistableIdleAction.Persist**.  
  
-   Cuando se indica a una aplicación host que conserve o descargue una instancia de flujo de trabajo.  
  
-   Cuándo se finaliza o termina una instancia de flujo de trabajo.  
  
-   Cuando un **Persist** actividad se ejecuta.  
  
-   Cuando una instancia de un flujo de trabajo desarrollada con una versión anterior de Windows Workflow Foundation encuentra un punto de persistencia durante la ejecución interoperable.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Almacén de instancias de flujo de trabajo de SQL](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)  
  
-   [Almacenes de instancias](../../../docs/framework/windows-workflow-foundation/instance-stores.md)  
  
-   [Participantes de persistencia](../../../docs/framework/windows-workflow-foundation/persistence-participants.md)  
  
-   [Procedimientos recomendados de persistencia](../../../docs/framework/windows-workflow-foundation/persistence-best-practices.md)  
  
-   [Instancias de flujo de trabajo no persistentes](../../../docs/framework/windows-workflow-foundation/non-persisted-workflow-instances.md)  
  
-   [Pausa y reanudación de un flujo de trabajo](../../../docs/framework/windows-workflow-foundation/pausing-and-resuming-a-workflow.md)
