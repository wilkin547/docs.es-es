---
title: Persistencia de flujo de trabajo
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], persistence
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
ms.openlocfilehash: c49e287c6132103d4bb85a8ae892a76f9b582274
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837537"
---
# <a name="workflow-persistence"></a>Persistencia de flujo de trabajo
La persistencia del flujo de trabajo es la captura duradera de un estado de la instancia de flujo de trabajo, independientemente de la información del proceso o del equipo. Esto sirve para proporcionar un punto de recuperación conocido para la instancia de flujo de trabajo en caso de error del sistema, para conservar la memoria descargando instancias de flujo de trabajo que no están funcionando de forma activa o para mover el estado de la instancia de flujo de trabajo de un nodo a otro en una granja de servidores.  
  
 La persistencia permite procesar la agilidad, escalabilidad, recuperación en caso de error y la capacidad de administrar la memoria más eficazmente. El proceso de persistencia incluye la identificación de un punto de persistencia, la recopilación de los datos que se van a guardar y finalmente la delegación del almacenamiento real de los datos a un proveedor de persistencia.  
  
 Para habilitar la persistencia de un flujo de trabajo, debe asociar un almacén de instancias con **WorkflowApplication** o **WorkflowServiceHost** tal y como se mencionó en [Cómo: habilitar la persistencia para flujos de trabajo y servicios de flujo de trabajo](how-to-enable-persistence-for-workflows-and-workflow-services.md). **WorkflowApplication** y **WorkflowServiceHost** usan el almacén de instancias asociado a ellos para habilitar la persistencia de las instancias de flujo de trabajo en un almacén de persistencia y cargar instancias de flujo de trabajo en memoria basándose en los datos de instancia de flujo de trabajo almacenados en el almacén de persistencia.  
  
 El [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] se suministra con la clase **SqlWorkflowInstanceStore** , que permite la persistencia de datos y metadatos sobre las instancias de flujo de trabajo en una base de datos SQL Server 2005 o SQL Server 2008. Vea [almacén de instancias de flujo de trabajo de SQL](sql-workflow-instance-store.md) para obtener más detalles.  
  
 Para almacenar y cargar los datos específicos de la aplicación junto con la información relacionada con la instancia de flujo de trabajo, puede crear participantes de persistencia que extienden la clase <xref:System.Activities.Persistence.PersistenceParticipant>. Los participantes de persistencia participan en el proceso de persistencia para guardar los datos serializables personalizados en el almacén de persistencia, para cargar los datos del almacén de instancias en la memoria y para realizar cualquier lógica adicional en una transacción de persistencia. Para obtener más información, consulte [participantes de persistencia](persistence-participants.md).  
  
 Windows Server APp Fabric simplifica el proceso de configuración de persistencia. Para obtener más información, vea [conceptos de persistencia con Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))  
  
## <a name="implicit-persistence-points"></a>Puntos de persistencia implícitos  
 La siguiente lista contiene ejemplos de las condiciones en las que se conserva un flujo de trabajo cuando se asocia un almacén de instancias a este.  
  
- Cuando se completa una actividad **TransactionScope** o se completa una actividad **TransactedReceiveScope** .  
  
- Cuando una instancia de flujo de trabajo se vuelve inactiva y **WorkflowIdleBehavior** se establece en el host del flujo de trabajo. Esto ocurre, por ejemplo, cuando se usan actividades de mensajería o una actividad de **retraso** .  
  
- Cuando una WorkflowApplication se vuelve inactiva y la propiedad **PersistableIdle** de la aplicación se establece en **PersistableIdleAction. Persist**.  
  
- Cuando se indica a una aplicación host que conserve o descargue una instancia de flujo de trabajo.  
  
- Cuándo se finaliza o termina una instancia de flujo de trabajo.  
  
- Cuando se ejecuta una actividad de **persistencia** .  
  
- Cuando una instancia de un flujo de trabajo desarrollada con una versión anterior de Windows Workflow Foundation encuentra un punto de persistencia durante la ejecución interoperable.  
  
## <a name="in-this-section"></a>Esta sección  
  
- [Almacén de instancias de flujo de trabajo de SQL](sql-workflow-instance-store.md)  
  
- [Almacenes de instancias](instance-stores.md)  
  
- [Participantes de persistencia](persistence-participants.md)  
  
- [Procedimientos recomendados de persistencia](persistence-best-practices.md)  
  
- [Instancias de flujo de trabajo no persistentes](non-persisted-workflow-instances.md)  
  
- [Pausa y reanudación de un flujo de trabajo](pausing-and-resuming-a-workflow.md)
