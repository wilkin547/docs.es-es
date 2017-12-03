---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2f99670d61df45edfef5350da080f12e892a0f74
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="322a3-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="322a3-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="322a3-103">La máquina de estado para una inscripción del coordinador ha entrado en el estado finalizado.</span><span class="sxs-lookup"><span data-stu-id="322a3-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="322a3-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="322a3-104">Description</span></span>  
 <span data-ttu-id="322a3-105">Se realiza un seguimiento cuando el administrador de transacciones local crea que una inscripción del coordinador superior ha completado el procesamiento de 2pc.</span><span class="sxs-lookup"><span data-stu-id="322a3-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="322a3-106">El resultado de la inscripción puede ser confirmado, anulado u olvidado.</span><span class="sxs-lookup"><span data-stu-id="322a3-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="322a3-107">También se realiza un seguimiento si el administrador de transacciones local vota ReadOnly durante la preparación.</span><span class="sxs-lookup"><span data-stu-id="322a3-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="322a3-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="322a3-108">See Also</span></span>  
 [<span data-ttu-id="322a3-109">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="322a3-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="322a3-110">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="322a3-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="322a3-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="322a3-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
