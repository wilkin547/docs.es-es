---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 7f37cb5d9ee3d2d9d56519f785388f278b3333b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997885"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="d419c-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="d419c-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="d419c-103">El equipo de estado para la inscripción de un participante introdujo el estado finalizado.</span><span class="sxs-lookup"><span data-stu-id="d419c-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d419c-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="d419c-104">Description</span></span>  
 <span data-ttu-id="d419c-105">Seguido cuando una inscripción de participante subordinado ha completado el procesamiento 2pc.</span><span class="sxs-lookup"><span data-stu-id="d419c-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="d419c-106">Se puede confirmar o anular el resultado de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="d419c-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="d419c-107">También se sigue si cualquier participante vota ReadOnly durante Prepare.</span><span class="sxs-lookup"><span data-stu-id="d419c-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d419c-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="d419c-108">See also</span></span>

- [<span data-ttu-id="d419c-109">Traza</span><span class="sxs-lookup"><span data-stu-id="d419c-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="d419c-110">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="d419c-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d419c-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d419c-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
