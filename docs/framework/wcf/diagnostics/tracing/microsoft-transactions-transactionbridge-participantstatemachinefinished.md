---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 0652b3b76c155431b68c5ee0dc8f83977f9845a5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594366"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="94cfc-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="94cfc-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="94cfc-103">El equipo de estado para la inscripción de un participante introdujo el estado finalizado.</span><span class="sxs-lookup"><span data-stu-id="94cfc-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="94cfc-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="94cfc-104">Description</span></span>  
 <span data-ttu-id="94cfc-105">Seguido cuando una inscripción de participante subordinado ha completado el procesamiento 2pc.</span><span class="sxs-lookup"><span data-stu-id="94cfc-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="94cfc-106">Se puede confirmar o anular el resultado de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="94cfc-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="94cfc-107">También se sigue si cualquier participante vota ReadOnly durante Prepare.</span><span class="sxs-lookup"><span data-stu-id="94cfc-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94cfc-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="94cfc-108">See also</span></span>

- [<span data-ttu-id="94cfc-109">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="94cfc-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="94cfc-110">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="94cfc-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="94cfc-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="94cfc-111">Administration and Diagnostics</span></span>](../index.md)
