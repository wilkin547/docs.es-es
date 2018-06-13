---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: fe88e70ab4955305d78baa1158cd73a93ba2ed2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33476325"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="1c312-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="1c312-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="1c312-103">El servicio de protocolo WS-AT recibió un mensaje de reproducción desde un participante duradero, que no respondió a la instrucción para preparar.</span><span class="sxs-lookup"><span data-stu-id="1c312-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="1c312-104">Por consiguiente, se anuló la transacción.</span><span class="sxs-lookup"><span data-stu-id="1c312-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1c312-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c312-105">Description</span></span>  
 <span data-ttu-id="1c312-106">Se realiza un seguimiento si se recibe un mensaje de reproducción mientras un participante duradero se está preparando.</span><span class="sxs-lookup"><span data-stu-id="1c312-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="1c312-107">Se trata de un mensaje no válido para este estado y se va a anular la transacción.</span><span class="sxs-lookup"><span data-stu-id="1c312-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="1c312-108">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="1c312-108">Troubleshooting</span></span>  
 <span data-ttu-id="1c312-109">Recibir este error puede indicar que un participante duradero (incluidos los administradores de transacciones subordinados) se ha recuperado del error, aunque no se sabe a ciencia cierta el resultado de la transacción y solicita su estado.</span><span class="sxs-lookup"><span data-stu-id="1c312-109">Receiving this error can indiate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure, however it is unsure of the transaction outcome and request its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c312-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c312-110">See Also</span></span>  
 [<span data-ttu-id="1c312-111">Traza</span><span class="sxs-lookup"><span data-stu-id="1c312-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="1c312-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="1c312-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="1c312-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1c312-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
