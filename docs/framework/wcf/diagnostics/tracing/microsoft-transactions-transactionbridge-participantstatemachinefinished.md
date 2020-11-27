---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: bd6c9124e6346437e2bb35df620e00bad13b60f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258951"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="2f14e-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="2f14e-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>

<span data-ttu-id="2f14e-103">El equipo de estado para la inscripción de un participante introdujo el estado finalizado.</span><span class="sxs-lookup"><span data-stu-id="2f14e-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2f14e-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f14e-104">Description</span></span>  

 <span data-ttu-id="2f14e-105">Seguido cuando una inscripción de participante subordinado ha completado el procesamiento 2pc.</span><span class="sxs-lookup"><span data-stu-id="2f14e-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="2f14e-106">Se puede confirmar o anular el resultado de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="2f14e-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="2f14e-107">También se sigue si cualquier participante vota ReadOnly durante Prepare.</span><span class="sxs-lookup"><span data-stu-id="2f14e-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f14e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f14e-108">See also</span></span>

- [<span data-ttu-id="2f14e-109">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="2f14e-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="2f14e-110">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="2f14e-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2f14e-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2f14e-111">Administration and Diagnostics</span></span>](../index.md)
