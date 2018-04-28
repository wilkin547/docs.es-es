---
title: Persistencia del flujo de trabajo
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- programming [WF], persistence
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2278762895978f90d80977f9e538b0e10a4f3f8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="workflow-persistence"></a><span data-ttu-id="85408-102">Persistencia del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="85408-102">Workflow Persistence</span></span>
<span data-ttu-id="85408-103">La persistencia del flujo de trabajo es la captura duradera de un estado de la instancia de flujo de trabajo, independientemente de la información del proceso o del equipo.</span><span class="sxs-lookup"><span data-stu-id="85408-103">Workflow persistence is the durable capture of a workflow instance's state, independent of process or computer information.</span></span> <span data-ttu-id="85408-104">Esto sirve para proporcionar un punto de recuperación conocido para la instancia de flujo de trabajo en caso de error del sistema, para conservar la memoria descargando instancias de flujo de trabajo que no están funcionando de forma activa o para mover el estado de la instancia de flujo de trabajo de un nodo a otro en una granja de servidores.</span><span class="sxs-lookup"><span data-stu-id="85408-104">This is done to provide a well-known point of recovery for the workflow instance in the event of system failure, or to preserve memory by unloading workflow instances that are not actively doing work, or to move the state of the workflow instance from one node to another node in a server farm.</span></span>  
  
 <span data-ttu-id="85408-105">La persistencia permite procesar la agilidad, escalabilidad, recuperación en caso de error y la capacidad de administrar la memoria más eficazmente.</span><span class="sxs-lookup"><span data-stu-id="85408-105">Persistence enables process agility, scalability, recovery in the face of failure, and the ability to manage memory more efficiently.</span></span> <span data-ttu-id="85408-106">El proceso de persistencia incluye la identificación de un punto de persistencia, la recopilación de los datos que se van a guardar y finalmente la delegación del almacenamiento real de los datos a un proveedor de persistencia.</span><span class="sxs-lookup"><span data-stu-id="85408-106">The persistence process includes the identification of a persistence point, the gathering of the data to be saved, and finally the delegation of the actual storage of the data to a persistence provider.</span></span>  
  
 <span data-ttu-id="85408-107">Para habilitar la persistencia para un flujo de trabajo, debe asociar un almacén de instancias con el **WorkflowApplication** o **WorkflowServiceHost** como se mencionó en [Cómo: habilitar la persistencia para Los flujos de trabajo y los servicios de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="85408-107">To enable persistence for a workflow, you need to associate an instance store with the **WorkflowApplication** or **WorkflowServiceHost** as mentioned in [How to: Enable Persistence for Workflows and Workflow Services](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="85408-108">El **WorkflowApplication** y **WorkflowServiceHost** usar el almacén de instancia asociado a ellos para habilitar la persistencia de instancias de flujo de trabajo en un almacén de persistencia y cargar instancias de flujo de trabajo en memoria en función de los datos de instancia de flujo de trabajo almacenados en el almacén de persistencia.</span><span class="sxs-lookup"><span data-stu-id="85408-108">The **WorkflowApplication** and **WorkflowServiceHost** use the instance store associated with them to enable persisting workflow instances into a persistence store and loading workflow instances into memory based on the workflow instance data stored in the persistence store.</span></span>  
  
 <span data-ttu-id="85408-109">El [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] se suministra con la **SqlWorkflowInstanceStore** (clase), que permite la persistencia de datos y metadatos acerca de las instancias de flujo de trabajo en una base de datos de SQL Server 2005 o SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="85408-109">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] ships with the **SqlWorkflowInstanceStore** class, which allows persistence of data and metadata about workflow instances into a SQL Server 2005 or SQL Server 2008 database.</span></span> <span data-ttu-id="85408-110">Vea [almacén de instancias de flujo de trabajo de SQL](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="85408-110">See [SQL Workflow Instance Store](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) for more details.</span></span>  
  
 <span data-ttu-id="85408-111">Para almacenar y cargar los datos específicos de la aplicación junto con la información relacionada con la instancia de flujo de trabajo, puede crear participantes de persistencia que extienden la clase <xref:System.Activities.Persistence.PersistenceParticipant>.</span><span class="sxs-lookup"><span data-stu-id="85408-111">To store and load your application-specific data along with the workflow instance-related information, you can create persistence participants that extend the <xref:System.Activities.Persistence.PersistenceParticipant> class.</span></span> <span data-ttu-id="85408-112">Los participantes de persistencia participan en el proceso de persistencia para guardar los datos serializables personalizados en el almacén de persistencia, para cargar los datos del almacén de instancias en la memoria y para realizar cualquier lógica adicional en una transacción de persistencia.</span><span class="sxs-lookup"><span data-stu-id="85408-112">A persistence participant participates in the persistence process to save custom serializable data into the persistence store, to load the data from the instance store into memory, and to perform any additional logic under a persistence transaction.</span></span> <span data-ttu-id="85408-113">Para obtener más información, consulte [participantes de persistencia](../../../docs/framework/windows-workflow-foundation/persistence-participants.md).</span><span class="sxs-lookup"><span data-stu-id="85408-113">For more information, see [Persistence Participants](../../../docs/framework/windows-workflow-foundation/persistence-participants.md).</span></span>  
  
 <span data-ttu-id="85408-114">Windows Server APp Fabric simplifica el proceso de configuración de persistencia.</span><span class="sxs-lookup"><span data-stu-id="85408-114">Windows Server App Fabric simplifies the process of configuring persistence.</span></span> <span data-ttu-id="85408-115">Para obtener más información, vea [conceptos de persistencia con Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201200)</span><span class="sxs-lookup"><span data-stu-id="85408-115">For more information, see [Persistence Concepts with Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201200)</span></span>  
  
## <a name="implicit-persistence-points"></a><span data-ttu-id="85408-116">Puntos de persistencia implícitos</span><span class="sxs-lookup"><span data-stu-id="85408-116">Implicit Persistence Points</span></span>  
 <span data-ttu-id="85408-117">La siguiente lista contiene ejemplos de las condiciones en las que se conserva un flujo de trabajo cuando se asocia un almacén de instancias a este.</span><span class="sxs-lookup"><span data-stu-id="85408-117">The following list contains examples of the conditions upon which a workflow is persisted when an instance store is associated with a workflow.</span></span>  
  
-   <span data-ttu-id="85408-118">Cuando un **TransactionScope** actividad se completa o una **TransactedReceiveScope** completa de la actividad.</span><span class="sxs-lookup"><span data-stu-id="85408-118">When a **TransactionScope** activity completes or a **TransactedReceiveScope** activity completes.</span></span>  
  
-   <span data-ttu-id="85408-119">Cuando una instancia de flujo de trabajo se vuelve inactiva y el **WorkflowIdleBehavior** se establece en el host de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="85408-119">When a workflow instance becomes idle and the **WorkflowIdleBehavior** is set on workflow host.</span></span> <span data-ttu-id="85408-120">Esto ocurre, por ejemplo, cuando use las actividades de mensajería o un **retraso** actividad.</span><span class="sxs-lookup"><span data-stu-id="85408-120">This occurs, for example, when you use messaging activities or a **Delay** activity.</span></span>  
  
-   <span data-ttu-id="85408-121">Cuando WorkflowApplication se vuelve inactiva y el **PersistableIdle** propiedad de la aplicación está establecida en **PersistableIdleAction.Persist**.</span><span class="sxs-lookup"><span data-stu-id="85408-121">When a WorkflowApplication becomes idle and the **PersistableIdle** property of the application is set to **PersistableIdleAction.Persist**.</span></span>  
  
-   <span data-ttu-id="85408-122">Cuando se indica a una aplicación host que conserve o descargue una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="85408-122">When a host application is instructed to persist or unload a workflow instance.</span></span>  
  
-   <span data-ttu-id="85408-123">Cuándo se finaliza o termina una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="85408-123">When a workflow instance is terminated or finishes.</span></span>  
  
-   <span data-ttu-id="85408-124">Cuando un **Persist** actividad se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="85408-124">When a **Persist** activity executes.</span></span>  
  
-   <span data-ttu-id="85408-125">Cuando una instancia de un flujo de trabajo desarrollada con una versión anterior de Windows Workflow Foundation encuentra un punto de persistencia durante la ejecución interoperable.</span><span class="sxs-lookup"><span data-stu-id="85408-125">When an instance of a workflow developed using a previous version of Windows Workflow Foundation encounters a persistence point during interoperable execution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85408-126">En esta sección</span><span class="sxs-lookup"><span data-stu-id="85408-126">In This Section</span></span>  
  
-   [<span data-ttu-id="85408-127">Almacén de instancias de flujo de trabajo de SQL</span><span class="sxs-lookup"><span data-stu-id="85408-127">SQL Workflow Instance Store</span></span>](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)  
  
-   [<span data-ttu-id="85408-128">Almacenes de instancias</span><span class="sxs-lookup"><span data-stu-id="85408-128">Instance Stores</span></span>](../../../docs/framework/windows-workflow-foundation/instance-stores.md)  
  
-   [<span data-ttu-id="85408-129">Participantes de persistencia</span><span class="sxs-lookup"><span data-stu-id="85408-129">Persistence Participants</span></span>](../../../docs/framework/windows-workflow-foundation/persistence-participants.md)  
  
-   [<span data-ttu-id="85408-130">Procedimientos recomendados de persistencia</span><span class="sxs-lookup"><span data-stu-id="85408-130">Persistence Best Practices</span></span>](../../../docs/framework/windows-workflow-foundation/persistence-best-practices.md)  
  
-   [<span data-ttu-id="85408-131">Instancias de flujo de trabajo no persistentes</span><span class="sxs-lookup"><span data-stu-id="85408-131">Non-Persisted Workflow Instances</span></span>](../../../docs/framework/windows-workflow-foundation/non-persisted-workflow-instances.md)  
  
-   [<span data-ttu-id="85408-132">Pausa y reanudación de un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="85408-132">Pausing and Resuming a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/pausing-and-resuming-a-workflow.md)
