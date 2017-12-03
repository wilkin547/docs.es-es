---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 845b344cee6c47a0c2f125caab7965ef8f65f336
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="56869-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="56869-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="56869-103">El equipo de estado para la inscripción de un participante introdujo el estado finalizado.</span><span class="sxs-lookup"><span data-stu-id="56869-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="56869-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="56869-104">Description</span></span>  
 <span data-ttu-id="56869-105">Seguido cuando una inscripción de participante subordinado ha completado el procesamiento 2pc.</span><span class="sxs-lookup"><span data-stu-id="56869-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="56869-106">Se puede confirmar o anular el resultado de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="56869-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="56869-107">También se sigue si cualquier participante vota ReadOnly durante Prepare.</span><span class="sxs-lookup"><span data-stu-id="56869-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56869-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="56869-108">See Also</span></span>  
 [<span data-ttu-id="56869-109">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="56869-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="56869-110">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="56869-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="56869-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="56869-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
