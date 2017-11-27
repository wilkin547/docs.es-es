---
title: "Actividades de transacción en WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f6132f1d9cbeef3ed7af5d2b711d04e8bd5755bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="transaction-activities-in-wf"></a>Actividades de transacción en WF
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] tiene varias actividades proporcionadas por el sistema para modelar transacciones, la compensación y la cancelación. Estos modelos de programación permiten que el flujo de trabajo continúe avanzando en caso de cambios en la lógica de negocios y el control de errores. [!INCLUDE[crabout](../../../includes/crabout-md.md)]las transacciones, compensación y la cancelación, consulte [transacciones](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md), [compensación](../../../docs/framework/windows-workflow-foundation/compensation.md), y [cancelación](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md).  
  
## <a name="transaction-activities"></a>Actividades de transacción  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|Asocia la lógica de cancelación, en forma de una actividad, con una ruta principal de ejecución, también expresada como una actividad.|  
|<xref:System.Activities.Statements.CompensableActivity>|Admite la compensación de las actividades secundarias.|  
|<xref:System.Activities.Statements.Compensate>|Invoca explícitamente el controlador de compensación de <xref:System.Activities.Statements.CompensableActivity>.|  
|<xref:System.Activities.Statements.Confirm>|Invoca explícitamente el controlador de confirmación de <xref:System.Activities.Statements.CompensableActivity>.|  
|<xref:System.Activities.Statements.TransactionScope>|Demarca el límite de una transacción.|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|Establece el ámbito de duración de una transacción que se inicia mediante un mensaje recibido. La transacción puede fluir en el flujo de trabajo del mensaje de inicio o la puede crear el distribuidor cuando se recibe el mensaje. **Nota:** el <xref:System.ServiceModel.Activities.TransactedReceiveScope> se encuentra en la **mensajería** sección de la **cuadro de herramientas**.|
