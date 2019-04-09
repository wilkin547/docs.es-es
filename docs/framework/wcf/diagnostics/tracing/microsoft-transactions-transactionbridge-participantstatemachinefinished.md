---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 7f37cb5d9ee3d2d9d56519f785388f278b3333b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170734"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="4d582-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="4d582-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="4d582-103">El equipo de estado para la inscripción de un participante introdujo el estado finalizado.</span><span class="sxs-lookup"><span data-stu-id="4d582-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4d582-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d582-104">Description</span></span>  
 <span data-ttu-id="4d582-105">Seguido cuando una inscripción de participante subordinado ha completado el procesamiento 2pc.</span><span class="sxs-lookup"><span data-stu-id="4d582-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="4d582-106">Se puede confirmar o anular el resultado de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="4d582-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="4d582-107">También se sigue si cualquier participante vota ReadOnly durante Prepare.</span><span class="sxs-lookup"><span data-stu-id="4d582-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d582-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d582-108">See also</span></span>

- [<span data-ttu-id="4d582-109">Traza</span><span class="sxs-lookup"><span data-stu-id="4d582-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="4d582-110">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="4d582-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="4d582-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="4d582-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
