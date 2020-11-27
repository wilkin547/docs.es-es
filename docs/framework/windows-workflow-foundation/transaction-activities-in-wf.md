---
title: Actividades de transacción en WF
ms.date: 03/30/2017
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
ms.openlocfilehash: c40799f7f0456a13ab975a766a36e9425a2144df
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293343"
---
# <a name="transaction-activities-in-wf"></a>Actividades de transacción en WF

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] tiene varias actividades proporcionadas por el sistema para modelar transacciones, la compensación y la cancelación. Estos modelos de programación permiten que el flujo de trabajo continúe avanzando en caso de cambios en la lógica de negocios y el control de errores. Para obtener más información sobre las transacciones, la compensación y la cancelación, vea [transacciones](workflow-transactions.md), [compensación](compensation.md)y [cancelación](modeling-cancellation-behavior-in-workflows.md).  
  
## <a name="transaction-activities"></a>Actividades de transacción  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|Asocia la lógica de cancelación, en forma de una actividad, con una ruta principal de ejecución, también expresada como una actividad.|  
|<xref:System.Activities.Statements.CompensableActivity>|Admite la compensación de las actividades secundarias.|  
|<xref:System.Activities.Statements.Compensate>|Invoca explícitamente el controlador de compensación de <xref:System.Activities.Statements.CompensableActivity>.|  
|<xref:System.Activities.Statements.Confirm>|Invoca explícitamente el controlador de confirmación de <xref:System.Activities.Statements.CompensableActivity>.|  
|<xref:System.Activities.Statements.TransactionScope>|Demarca el límite de una transacción.|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|Establece el ámbito de duración de una transacción que se inicia mediante un mensaje recibido. La transacción puede fluir en el flujo de trabajo del mensaje de inicio o la puede crear el distribuidor cuando se recibe el mensaje. **Nota:**  <xref:System.ServiceModel.Activities.TransactedReceiveScope> Se encuentra en la sección **Mensajería** del cuadro de **herramientas**.|
