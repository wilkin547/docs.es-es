---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: 22992b4dfad4b4867adda0fcbbd8ecc5eb67d87e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997612"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="0c447-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="0c447-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="0c447-103">El servicio de protocolo WS-AT superó el tiempo de espera de una respuesta a un mensaje de salida de un participante volátil.</span><span class="sxs-lookup"><span data-stu-id="0c447-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="0c447-104">El resultado de la transacción puede estar en duda si el participante vuelve.</span><span class="sxs-lookup"><span data-stu-id="0c447-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0c447-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c447-105">Description</span></span>  
 <span data-ttu-id="0c447-106">Se le hace seguimiento si un participante volátil ha decidido Confirmar o Anular, pero no ha respondido a una solicitud de confirmación o recuperación dentro de un período determinado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="0c447-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="0c447-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="0c447-107">Troubleshooting</span></span>  
 <span data-ttu-id="0c447-108">Asegúrese de que todos los participantes volátiles pueden responder dentro del período de tiempo dado.</span><span class="sxs-lookup"><span data-stu-id="0c447-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="0c447-109">El período de tiempo predeterminado es de 180 segundos.</span><span class="sxs-lookup"><span data-stu-id="0c447-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="0c447-110">Si esto es insuficiente, aumente la directiva de temporizador `VolatileOutcomeDelay` para WS-AT.</span><span class="sxs-lookup"><span data-stu-id="0c447-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c447-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c447-111">See also</span></span>

- [<span data-ttu-id="0c447-112">Traza</span><span class="sxs-lookup"><span data-stu-id="0c447-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="0c447-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="0c447-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="0c447-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="0c447-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
