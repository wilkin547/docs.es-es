---
description: 'Más información acerca de: Microsoft. Transactions. TransactionBridge. ParticipantStateMachineFinished'
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: f49027b82957969779423d0895ff24a4a36d1f4f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759385"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="86b78-103">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="86b78-103">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>

<span data-ttu-id="86b78-104">El equipo de estado para la inscripción de un participante introdujo el estado finalizado.</span><span class="sxs-lookup"><span data-stu-id="86b78-104">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="86b78-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="86b78-105">Description</span></span>  

 <span data-ttu-id="86b78-106">Seguido cuando una inscripción de participante subordinado ha completado el procesamiento 2pc.</span><span class="sxs-lookup"><span data-stu-id="86b78-106">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="86b78-107">Se puede confirmar o anular el resultado de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="86b78-107">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="86b78-108">También se sigue si cualquier participante vota ReadOnly durante Prepare.</span><span class="sxs-lookup"><span data-stu-id="86b78-108">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86b78-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="86b78-109">See also</span></span>

- [<span data-ttu-id="86b78-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="86b78-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="86b78-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="86b78-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="86b78-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="86b78-112">Administration and Diagnostics</span></span>](../index.md)
