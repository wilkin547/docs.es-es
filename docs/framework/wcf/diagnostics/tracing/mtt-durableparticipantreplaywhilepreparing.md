---
description: 'Más información acerca de: Microsoft. Transactions. TransactionBridge. DurableParticipantReplayWhilePreparing'
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: fcaa50dd4faa548cad8ff085f1c66f94c63bd010
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99635667"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="5e9d6-103">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="5e9d6-103">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>

<span data-ttu-id="5e9d6-104">El servicio de protocolo WS-AT recibió un mensaje de reproducción desde un participante duradero, que no respondió a la instrucción para preparar.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-104">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="5e9d6-105">Por consiguiente, se anuló la transacción.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-105">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5e9d6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e9d6-106">Description</span></span>  

 <span data-ttu-id="5e9d6-107">Se realiza un seguimiento si se recibe un mensaje de reproducción mientras un participante duradero se está preparando.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-107">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="5e9d6-108">Se trata de un mensaje no válido para este estado y se va a anular la transacción.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-108">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="5e9d6-109">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="5e9d6-109">Troubleshooting</span></span>

<span data-ttu-id="5e9d6-110">Recibir este error puede indicar que un participante duradero (incluido el TransactionManagers subordinado) se ha recuperado de un error. sin embargo, no está seguro del resultado de la transacción y solicita su estado.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-110">Receiving this error can indicate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure; however, it is unsure of the transaction outcome and requests its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e9d6-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e9d6-111">See also</span></span>

- [<span data-ttu-id="5e9d6-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="5e9d6-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="5e9d6-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="5e9d6-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="5e9d6-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5e9d6-114">Administration and Diagnostics</span></span>](../index.md)
