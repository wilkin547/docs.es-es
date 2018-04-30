---
title: punto de conexión de control de flujo de trabajo
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b883334-1590-4fbb-b0d6-65197efe0700
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3cd72919acd8e6392d809f22ddd87042d00008f6
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="workflow-control-endpoint"></a>punto de conexión de control de flujo de trabajo
El extremo de control de flujo de trabajo permite a los desarrolladores llamar a las operaciones de control para controlar de forma remota instancias de flujo de trabajo hospedadas mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Esta característica se puede utilizar para realizar operaciones de control mediante programación como la suspensión, la reanudación y la finalización.  
  
> [!WARNING]
>  Si usa el extremo de control de flujo de trabajo dentro de una transacción y el flujo de trabajo que se controla contiene una actividad <xref:System.Activities.Statements.Persist>, la instancia de flujo de trabajo no responderá hasta que se agote el tiempo de espera de la transacción.  
  
## <a name="workflow-instance-management"></a>Administración de instancias de flujo de trabajo  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] define un nuevo contrato llamado <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement>. Este contrato define una serie de operaciones de control que le permiten controlar de forma remota instancias de flujo de trabajo hospedadas por <xref:System.ServiceModel.Activities.WorkflowServiceHost>. <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> es un extremo estándar que proporciona una implementación del contrato de <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement>. <xref:System.ServiceModel.Activities.WorkflowControlClient> es una clase que se usa para enviar operaciones de control a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.  
  
 Las instancias de flujo de trabajo pueden presentar uno de los estados siguientes:  
  
 Activo  
 El estado de una instancia de flujo de trabajo antes de alcanzar el estado completado y cuando no se encuentra en estado suspendido. Cuando se encuentra en este estado, la instancia de flujo de trabajo se ejecuta y procesa los mensajes de aplicación.  
  
 Suspendido  
 Cuando se encuentra en este estado, la instancia de flujo de trabajo no se ejecuta aunque haya actividades que no hayan comenzado a ejecutarse o se han ejecutado parcialmente.  
  
 Completado  
 El estado final de una instancia de flujo de trabajo. La instancia de flujo de trabajo no se puede ejecutar después de alcanzar el estado completado.  
  
## <a name="iworkflowinstancemanagement"></a>IWorkflowInstanceManagement  
 La interfaz <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement> define un conjunto de operaciones de control con versiones sincrónicas y asincrónicas. Las versiones de transacción requieren el uso de un enlace que reconoce las transacciones. En la siguiente tabla, se enumeran las operaciones de control admitidas.  
  
|Operación de control|Descripción|  
|-----------------------|-----------------|  
|Abort|Detiene de forma obligatoria la ejecución de la instancia de flujo de trabajo.|  
|Cancelar|Realiza una transición de una instancia de flujo de trabajo del estado activo o suspendido al estado completado.|  
|Run|Ofrece a una instancia de flujo de trabajo la oportunidad de ejecutarse.|  
|Suspender|Realiza una transición de una instancia de flujo de trabajo del estado activo al estado suspendido.|  
|Terminar|Realiza una transición de una instancia de flujo de trabajo del estado activo o suspendido al estado completado.|  
|Unsuspend|Realiza una transición de una instancia de flujo de trabajo del estado suspendido al estado activo.|  
|TransactedCancel|Realiza la operación de cancelación en una transacción (procedente del cliente o creada localmente). Si el sistema mantiene el estado durable de la instancia de flujo de trabajo, la instancia de flujo de trabajo se debe conservar durante la ejecución de esta operación.|  
|TransactedRun|Realiza la operación de ejecución en una transacción (procedente del cliente o creada localmente). Si el sistema mantiene el estado durable de la instancia de flujo de trabajo, la instancia de flujo de trabajo se debe conservar durante la ejecución de esta operación.|  
|TransactedSuspend|Realiza la operación de suspensión en una transacción (procedente del cliente o creada localmente). Si el sistema mantiene el estado durable de la instancia de flujo de trabajo, la instancia de flujo de trabajo se debe conservar durante la ejecución de esta operación.|  
|TransactedTerminate|Realiza la operación de finalización en una transacción (procedente del cliente o creada localmente). Si el sistema mantiene el estado durable de la instancia de flujo de trabajo, la instancia de flujo de trabajo se debe conservar durante la ejecución de esta operación.|  
|TransactedUnsuspend|Realiza la operación de cancelación de la suspensión en una transacción (procedente del cliente o creada localmente). Si el sistema mantiene el estado durable de la instancia de flujo de trabajo, la instancia de flujo de trabajo se debe conservar durante la ejecución de esta operación.|  
  
 El contrato de <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement> no proporciona un medio para crear una nueva instancia de flujo de trabajo, solo para administrar instancias de flujo de trabajo existentes. Para obtener más información acerca de cómo crear una nueva instancia de flujo de trabajo de forma remota, consulte [extensibilidad de Host de servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="workflowcontrolendpoint"></a>WorkflowControlEndpoint  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> es un extremo estándar con un contrato fijo, <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement>. Cuando se agrega a una instancia de <xref:System.ServiceModel.Activities.WorkflowServiceHost>, este extremo se puede usar para enviar operaciones de comando a cualquier instancia de flujo de trabajo hospedada por la instancia del host. Para obtener más información acerca de los puntos de conexión estándares, consulte [puntos de conexión estándar](../../../../docs/framework/wcf/feature-details/standard-endpoints.md).  
  
## <a name="workflowcontrolclient"></a>WorkflowControlClient  
 <xref:System.ServiceModel.Activities.WorkflowControlClient> es una clase que le permite enviar mensajes de control a una clase <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> en una clase <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Contiene un método para cada una de las operaciones admitidas por el contrato de <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement> excepto para las operaciones con transacciones. <xref:System.ServiceModel.Activities.WorkflowControlClient> usa la transacción ambiente para determinar si se debe usar una operación con transacciones.
