---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: bc2cdc2221ec522b44c36ef3320b77124d61850e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236707"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="4ef6f-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="4ef6f-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>

<span data-ttu-id="4ef6f-103">El servicio de protocolo WS-AT superó el tiempo de espera de una respuesta a un mensaje de salida de un participante volátil.</span><span class="sxs-lookup"><span data-stu-id="4ef6f-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="4ef6f-104">El resultado de la transacción puede estar en duda si el participante vuelve.</span><span class="sxs-lookup"><span data-stu-id="4ef6f-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4ef6f-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ef6f-105">Description</span></span>  

 <span data-ttu-id="4ef6f-106">Se le hace seguimiento si un participante volátil ha decidido Confirmar o Anular, pero no ha respondido a una solicitud de confirmación o recuperación dentro de un período determinado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="4ef6f-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="4ef6f-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="4ef6f-107">Troubleshooting</span></span>  

 <span data-ttu-id="4ef6f-108">Asegúrese de que todos los participantes volátiles pueden responder dentro del período de tiempo dado.</span><span class="sxs-lookup"><span data-stu-id="4ef6f-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="4ef6f-109">El período de tiempo predeterminado es de 180 segundos.</span><span class="sxs-lookup"><span data-stu-id="4ef6f-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="4ef6f-110">Si esto es insuficiente, aumente la directiva de temporizador `VolatileOutcomeDelay` para WS-AT.</span><span class="sxs-lookup"><span data-stu-id="4ef6f-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ef6f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ef6f-111">See also</span></span>

- [<span data-ttu-id="4ef6f-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="4ef6f-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="4ef6f-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="4ef6f-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="4ef6f-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="4ef6f-114">Administration and Diagnostics</span></span>](../index.md)
