---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: 93354fbdd0c1726280526ca07a8b3dd1c57c8a25
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486769"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="9ffc5-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="9ffc5-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="9ffc5-103">El servicio de protocolo WS-AT recibió un mensaje de reproducción desde un participante duradero, que no respondió a la instrucción para preparar.</span><span class="sxs-lookup"><span data-stu-id="9ffc5-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="9ffc5-104">Por consiguiente, se anuló la transacción.</span><span class="sxs-lookup"><span data-stu-id="9ffc5-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9ffc5-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ffc5-105">Description</span></span>  
 <span data-ttu-id="9ffc5-106">Se realiza un seguimiento si se recibe un mensaje de reproducción mientras un participante duradero se está preparando.</span><span class="sxs-lookup"><span data-stu-id="9ffc5-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="9ffc5-107">Se trata de un mensaje no válido para este estado y se va a anular la transacción.</span><span class="sxs-lookup"><span data-stu-id="9ffc5-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="9ffc5-108">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="9ffc5-108">Troubleshooting</span></span>

<span data-ttu-id="9ffc5-109">Este error puede indicar que un participante duradero (incluidos los administradores de transacciones subordinados) se ha recuperado del error; Sin embargo, es seguro del resultado de la transacción y solicita su estado.</span><span class="sxs-lookup"><span data-stu-id="9ffc5-109">Receiving this error can indicate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure; however, it is unsure of the transaction outcome and requests its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ffc5-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ffc5-110">See also</span></span>

- [<span data-ttu-id="9ffc5-111">Traza</span><span class="sxs-lookup"><span data-stu-id="9ffc5-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="9ffc5-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="9ffc5-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="9ffc5-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="9ffc5-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
