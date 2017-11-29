---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1992a209bb58c0a0d6f181eb2f1ec546d50372ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="b0f0e-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="b0f0e-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="b0f0e-103">El servicio de protocolo WS-AT superó el tiempo de espera de una respuesta a un mensaje de salida de un participante volátil.</span><span class="sxs-lookup"><span data-stu-id="b0f0e-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="b0f0e-104">El resultado de la transacción puede estar en duda si el participante vuelve.</span><span class="sxs-lookup"><span data-stu-id="b0f0e-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b0f0e-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0f0e-105">Description</span></span>  
 <span data-ttu-id="b0f0e-106">Se le hace seguimiento si un participante volátil ha decidido Confirmar o Anular, pero no ha respondido a una solicitud de confirmación o recuperación dentro de un período determinado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="b0f0e-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="b0f0e-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="b0f0e-107">Troubleshooting</span></span>  
 <span data-ttu-id="b0f0e-108">Asegúrese de que todos los participantes volátiles pueden responder dentro del período de tiempo dado.</span><span class="sxs-lookup"><span data-stu-id="b0f0e-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="b0f0e-109">El período de tiempo predeterminado es de 180 segundos.</span><span class="sxs-lookup"><span data-stu-id="b0f0e-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="b0f0e-110">Si esto es insuficiente, aumente la directiva de temporizador `VolatileOutcomeDelay` para WS-AT.</span><span class="sxs-lookup"><span data-stu-id="b0f0e-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0f0e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0f0e-111">See Also</span></span>  
 [<span data-ttu-id="b0f0e-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="b0f0e-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="b0f0e-113">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b0f0e-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="b0f0e-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b0f0e-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
