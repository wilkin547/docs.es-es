---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: 3b9a3703e49c3932f62fcfb6994c9028b074bbe8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594418"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="7c4d5-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="7c4d5-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="7c4d5-103">La máquina de estado para una inscripción del coordinador ha entrado en el estado finalizado.</span><span class="sxs-lookup"><span data-stu-id="7c4d5-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7c4d5-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c4d5-104">Description</span></span>  
 <span data-ttu-id="7c4d5-105">Se realiza un seguimiento cuando el administrador de transacciones local crea que una inscripción del coordinador superior ha completado el procesamiento de 2pc.</span><span class="sxs-lookup"><span data-stu-id="7c4d5-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="7c4d5-106">El resultado de la inscripción puede ser confirmado, anulado u olvidado.</span><span class="sxs-lookup"><span data-stu-id="7c4d5-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="7c4d5-107">También se realiza un seguimiento si el administrador de transacciones local vota ReadOnly durante la preparación.</span><span class="sxs-lookup"><span data-stu-id="7c4d5-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c4d5-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c4d5-108">See also</span></span>

- [<span data-ttu-id="7c4d5-109">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="7c4d5-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="7c4d5-110">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="7c4d5-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="7c4d5-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="7c4d5-111">Administration and Diagnostics</span></span>](../index.md)
