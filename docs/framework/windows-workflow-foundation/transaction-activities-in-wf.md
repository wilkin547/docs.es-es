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
# <a name="transaction-activities-in-wf"></a><span data-ttu-id="820bb-102">Actividades de transacción en WF</span><span class="sxs-lookup"><span data-stu-id="820bb-102">Transaction Activities in WF</span></span>

<span data-ttu-id="820bb-103">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] tiene varias actividades proporcionadas por el sistema para modelar transacciones, la compensación y la cancelación.</span><span class="sxs-lookup"><span data-stu-id="820bb-103">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] has several system-provided activities for modeling transactions, compensation, and cancellation.</span></span> <span data-ttu-id="820bb-104">Estos modelos de programación permiten que el flujo de trabajo continúe avanzando en caso de cambios en la lógica de negocios y el control de errores.</span><span class="sxs-lookup"><span data-stu-id="820bb-104">These programming models allow the workflow to continue forward progress in the event of changes in business logic and error handling.</span></span> <span data-ttu-id="820bb-105">Para obtener más información sobre las transacciones, la compensación y la cancelación, vea [transacciones](workflow-transactions.md), [compensación](compensation.md)y [cancelación](modeling-cancellation-behavior-in-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="820bb-105">For more information about transactions, compensation, and cancellation, see [Transactions](workflow-transactions.md), [Compensation](compensation.md), and [Cancellation](modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
## <a name="transaction-activities"></a><span data-ttu-id="820bb-106">Actividades de transacción</span><span class="sxs-lookup"><span data-stu-id="820bb-106">Transaction Activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|<span data-ttu-id="820bb-107">Asocia la lógica de cancelación, en forma de una actividad, con una ruta principal de ejecución, también expresada como una actividad.</span><span class="sxs-lookup"><span data-stu-id="820bb-107">Associates cancellation logic, in the form of an activity, with a main path of execution, also expressed as an activity.</span></span>|  
|<xref:System.Activities.Statements.CompensableActivity>|<span data-ttu-id="820bb-108">Admite la compensación de las actividades secundarias.</span><span class="sxs-lookup"><span data-stu-id="820bb-108">Supports compensation of its child activities.</span></span>|  
|<xref:System.Activities.Statements.Compensate>|<span data-ttu-id="820bb-109">Invoca explícitamente el controlador de compensación de <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="820bb-109">Explicitly invokes the compensation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.Confirm>|<span data-ttu-id="820bb-110">Invoca explícitamente el controlador de confirmación de <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="820bb-110">Explicitly invokes the confirmation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.TransactionScope>|<span data-ttu-id="820bb-111">Demarca el límite de una transacción.</span><span class="sxs-lookup"><span data-stu-id="820bb-111">Demarcates a transaction boundary.</span></span>|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|<span data-ttu-id="820bb-112">Establece el ámbito de duración de una transacción que se inicia mediante un mensaje recibido.</span><span class="sxs-lookup"><span data-stu-id="820bb-112">Scopes the lifetime of a transaction that is initiated by a received message.</span></span> <span data-ttu-id="820bb-113">La transacción puede fluir en el flujo de trabajo del mensaje de inicio o la puede crear el distribuidor cuando se recibe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="820bb-113">The transaction may be flowed into the workflow on the initiating message, or created by the dispatcher when the message is received.</span></span> <span data-ttu-id="820bb-114">**Nota:**  <xref:System.ServiceModel.Activities.TransactedReceiveScope> Se encuentra en la sección **Mensajería** del cuadro de **herramientas**.</span><span class="sxs-lookup"><span data-stu-id="820bb-114">**Note:**  The <xref:System.ServiceModel.Activities.TransactedReceiveScope> is located in the **Messaging** section of the **Toolbox**.</span></span>|
