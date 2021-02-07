---
description: 'Más información acerca de: Microsoft. Transactions. TransactionBridge. CoordinatorStateMachineFinished'
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: 83cbc6fe80d0fc611c88e8074805cae870261305
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759398"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="6e3e5-103">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="6e3e5-103">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>

<span data-ttu-id="6e3e5-104">La máquina de estado para una inscripción del coordinador ha entrado en el estado finalizado.</span><span class="sxs-lookup"><span data-stu-id="6e3e5-104">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6e3e5-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e3e5-105">Description</span></span>  

 <span data-ttu-id="6e3e5-106">Se realiza un seguimiento cuando el administrador de transacciones local crea que una inscripción del coordinador superior ha completado el procesamiento de 2pc.</span><span class="sxs-lookup"><span data-stu-id="6e3e5-106">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="6e3e5-107">El resultado de la inscripción puede ser confirmado, anulado u olvidado.</span><span class="sxs-lookup"><span data-stu-id="6e3e5-107">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="6e3e5-108">También se realiza un seguimiento si el administrador de transacciones local vota ReadOnly durante la preparación.</span><span class="sxs-lookup"><span data-stu-id="6e3e5-108">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e3e5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e3e5-109">See also</span></span>

- [<span data-ttu-id="6e3e5-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="6e3e5-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="6e3e5-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="6e3e5-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6e3e5-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="6e3e5-112">Administration and Diagnostics</span></span>](../index.md)
