---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: dd2a0b67ec140aa2e6fe1abad8e85c0206abd8ea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579026"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="1c360-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="1c360-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="1c360-103">El servicio de protocolo WS-AT superó el tiempo de espera de una respuesta a un mensaje de salida de un participante volátil.</span><span class="sxs-lookup"><span data-stu-id="1c360-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="1c360-104">El resultado de la transacción puede estar en duda si el participante vuelve.</span><span class="sxs-lookup"><span data-stu-id="1c360-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1c360-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c360-105">Description</span></span>  
 <span data-ttu-id="1c360-106">Se le hace seguimiento si un participante volátil ha decidido Confirmar o Anular, pero no ha respondido a una solicitud de confirmación o recuperación dentro de un período determinado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="1c360-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="1c360-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="1c360-107">Troubleshooting</span></span>  
 <span data-ttu-id="1c360-108">Asegúrese de que todos los participantes volátiles pueden responder dentro del período de tiempo dado.</span><span class="sxs-lookup"><span data-stu-id="1c360-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="1c360-109">El período de tiempo predeterminado es de 180 segundos.</span><span class="sxs-lookup"><span data-stu-id="1c360-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="1c360-110">Si esto es insuficiente, aumente la directiva de temporizador `VolatileOutcomeDelay` para WS-AT.</span><span class="sxs-lookup"><span data-stu-id="1c360-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c360-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c360-111">See also</span></span>

- [<span data-ttu-id="1c360-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="1c360-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="1c360-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="1c360-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1c360-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1c360-114">Administration and Diagnostics</span></span>](../index.md)
