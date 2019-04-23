---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: bffaed4976d82202eaea9ce50f6d389548fdabfd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144838"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="72e15-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="72e15-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="72e15-103">La máquina de estado para una inscripción del coordinador ha entrado en el estado finalizado.</span><span class="sxs-lookup"><span data-stu-id="72e15-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="72e15-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="72e15-104">Description</span></span>  
 <span data-ttu-id="72e15-105">Se realiza un seguimiento cuando el administrador de transacciones local crea que una inscripción del coordinador superior ha completado el procesamiento de 2pc.</span><span class="sxs-lookup"><span data-stu-id="72e15-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="72e15-106">El resultado de la inscripción puede ser confirmado, anulado u olvidado.</span><span class="sxs-lookup"><span data-stu-id="72e15-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="72e15-107">También se realiza un seguimiento si el administrador de transacciones local vota ReadOnly durante la preparación.</span><span class="sxs-lookup"><span data-stu-id="72e15-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72e15-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="72e15-108">See also</span></span>

- [<span data-ttu-id="72e15-109">Traza</span><span class="sxs-lookup"><span data-stu-id="72e15-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="72e15-110">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="72e15-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="72e15-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="72e15-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
