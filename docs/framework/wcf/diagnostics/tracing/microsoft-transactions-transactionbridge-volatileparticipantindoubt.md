---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3b497231326c640b93b96500df39732104e0f0c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="949db-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="949db-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="949db-103">El servicio de protocolo WS-AT recibió un mensaje Prepared o Repay desde un participante volátil desconocido.</span><span class="sxs-lookup"><span data-stu-id="949db-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="949db-104">Se devolvió un error al participante, declara que el resultado de la transacción es dudoso.</span><span class="sxs-lookup"><span data-stu-id="949db-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="949db-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="949db-105">Description</span></span>  
 <span data-ttu-id="949db-106">Se realiza un seguimiento si el Administrador de transacciones local recibe un mensaje Prepared o Replay desde una inscripción volátil de la que ya se ha olvidado.</span><span class="sxs-lookup"><span data-stu-id="949db-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="949db-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="949db-107">Troubleshooting</span></span>  
 <span data-ttu-id="949db-108">Investigue las causas potenciales de los últimos mensajes que proceden del participante volátil.</span><span class="sxs-lookup"><span data-stu-id="949db-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="949db-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="949db-109">See Also</span></span>  
 [<span data-ttu-id="949db-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="949db-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="949db-111">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="949db-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="949db-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="949db-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
