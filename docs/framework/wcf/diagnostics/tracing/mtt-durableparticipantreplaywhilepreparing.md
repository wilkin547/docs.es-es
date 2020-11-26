---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: bfa279887339f025e4cb7c9c455fd25098684073
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236616"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="f8962-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="f8962-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>

<span data-ttu-id="f8962-103">El servicio de protocolo WS-AT recibió un mensaje de reproducción desde un participante duradero, que no respondió a la instrucción para preparar.</span><span class="sxs-lookup"><span data-stu-id="f8962-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="f8962-104">Por consiguiente, se anuló la transacción.</span><span class="sxs-lookup"><span data-stu-id="f8962-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f8962-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8962-105">Description</span></span>  

 <span data-ttu-id="f8962-106">Se realiza un seguimiento si se recibe un mensaje de reproducción mientras un participante duradero se está preparando.</span><span class="sxs-lookup"><span data-stu-id="f8962-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="f8962-107">Se trata de un mensaje no válido para este estado y se va a anular la transacción.</span><span class="sxs-lookup"><span data-stu-id="f8962-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="f8962-108">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="f8962-108">Troubleshooting</span></span>

<span data-ttu-id="f8962-109">Recibir este error puede indicar que un participante duradero (incluido el TransactionManagers subordinado) se ha recuperado de un error. sin embargo, no está seguro del resultado de la transacción y solicita su estado.</span><span class="sxs-lookup"><span data-stu-id="f8962-109">Receiving this error can indicate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure; however, it is unsure of the transaction outcome and requests its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8962-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8962-110">See also</span></span>

- [<span data-ttu-id="f8962-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="f8962-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="f8962-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="f8962-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="f8962-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="f8962-113">Administration and Diagnostics</span></span>](../index.md)
