---
description: 'Más información acerca de: Microsoft. Transactions. TransactionBridge. VolatileParticipantInDoubt'
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: c9d95285e09d017aa82c86e7c5c6f9fd758b9f80
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803248"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="2edcd-103">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="2edcd-103">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>

<span data-ttu-id="2edcd-104">El servicio de protocolo WS-AT recibió un mensaje Prepared o Repay desde un participante volátil desconocido.</span><span class="sxs-lookup"><span data-stu-id="2edcd-104">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="2edcd-105">Se devolvió un error al participante, declara que el resultado de la transacción es dudoso.</span><span class="sxs-lookup"><span data-stu-id="2edcd-105">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2edcd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2edcd-106">Description</span></span>  

 <span data-ttu-id="2edcd-107">Se realiza un seguimiento si el Administrador de transacciones local recibe un mensaje Prepared o Replay desde una inscripción volátil de la que ya se ha olvidado.</span><span class="sxs-lookup"><span data-stu-id="2edcd-107">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2edcd-108">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="2edcd-108">Troubleshooting</span></span>  

 <span data-ttu-id="2edcd-109">Investigue las causas potenciales de los últimos mensajes que proceden del participante volátil.</span><span class="sxs-lookup"><span data-stu-id="2edcd-109">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2edcd-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2edcd-110">See also</span></span>

- [<span data-ttu-id="2edcd-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="2edcd-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="2edcd-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="2edcd-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2edcd-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2edcd-113">Administration and Diagnostics</span></span>](../index.md)
