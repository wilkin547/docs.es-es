---
description: 'Más información acerca de: Microsoft. Transactions. TransactionBridge. VolatileOutcomeTimeout'
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: 5dd6ecce995d315581e1335e4dc83c425a6381b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677241"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="b6a18-103">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="b6a18-103">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>

<span data-ttu-id="b6a18-104">El servicio de protocolo WS-AT superó el tiempo de espera de una respuesta a un mensaje de salida de un participante volátil.</span><span class="sxs-lookup"><span data-stu-id="b6a18-104">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="b6a18-105">El resultado de la transacción puede estar en duda si el participante vuelve.</span><span class="sxs-lookup"><span data-stu-id="b6a18-105">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b6a18-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6a18-106">Description</span></span>  

 <span data-ttu-id="b6a18-107">Se le hace seguimiento si un participante volátil ha decidido Confirmar o Anular, pero no ha respondido a una solicitud de confirmación o recuperación dentro de un período determinado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="b6a18-107">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="b6a18-108">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="b6a18-108">Troubleshooting</span></span>  

 <span data-ttu-id="b6a18-109">Asegúrese de que todos los participantes volátiles pueden responder dentro del período de tiempo dado.</span><span class="sxs-lookup"><span data-stu-id="b6a18-109">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="b6a18-110">El período de tiempo predeterminado es de 180 segundos.</span><span class="sxs-lookup"><span data-stu-id="b6a18-110">The default time period is 180 seconds.</span></span>  <span data-ttu-id="b6a18-111">Si esto es insuficiente, aumente la directiva de temporizador `VolatileOutcomeDelay` para WS-AT.</span><span class="sxs-lookup"><span data-stu-id="b6a18-111">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6a18-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6a18-112">See also</span></span>

- [<span data-ttu-id="b6a18-113">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="b6a18-113">Tracing</span></span>](index.md)
- [<span data-ttu-id="b6a18-114">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="b6a18-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b6a18-115">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b6a18-115">Administration and Diagnostics</span></span>](../index.md)
