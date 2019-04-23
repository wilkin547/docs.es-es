---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: f5d74d73cc43b500d3920ca03905f4eb7543619a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075540"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="c8fe9-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="c8fe9-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="c8fe9-103">El servicio de protocolo WS-AT recibió un mensaje de reproducción desde un participante duradero, que no respondió a la instrucción para preparar.</span><span class="sxs-lookup"><span data-stu-id="c8fe9-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="c8fe9-104">Por consiguiente, se anuló la transacción.</span><span class="sxs-lookup"><span data-stu-id="c8fe9-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c8fe9-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8fe9-105">Description</span></span>  
 <span data-ttu-id="c8fe9-106">Se realiza un seguimiento si se recibe un mensaje de reproducción mientras un participante duradero se está preparando.</span><span class="sxs-lookup"><span data-stu-id="c8fe9-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="c8fe9-107">Se trata de un mensaje no válido para este estado y se va a anular la transacción.</span><span class="sxs-lookup"><span data-stu-id="c8fe9-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="c8fe9-108">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="c8fe9-108">Troubleshooting</span></span>  
 <span data-ttu-id="c8fe9-109">Recibir este error puede indicar que un participante duradero (incluidos los administradores de transacciones subordinados) se ha recuperado del error, aunque no se sabe a ciencia cierta el resultado de la transacción y solicita su estado.</span><span class="sxs-lookup"><span data-stu-id="c8fe9-109">Receiving this error can indiate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure, however it is unsure of the transaction outcome and request its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8fe9-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8fe9-110">See also</span></span>

- [<span data-ttu-id="c8fe9-111">Traza</span><span class="sxs-lookup"><span data-stu-id="c8fe9-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="c8fe9-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="c8fe9-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c8fe9-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c8fe9-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
