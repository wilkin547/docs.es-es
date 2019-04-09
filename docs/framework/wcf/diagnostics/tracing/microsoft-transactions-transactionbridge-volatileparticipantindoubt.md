---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: 9434f2f902a50a37fb3efee22fd3b18b33af9129
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138975"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="3f25e-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="3f25e-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="3f25e-103">El servicio de protocolo WS-AT recibió un mensaje Prepared o Repay desde un participante volátil desconocido.</span><span class="sxs-lookup"><span data-stu-id="3f25e-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="3f25e-104">Se devolvió un error al participante, declara que el resultado de la transacción es dudoso.</span><span class="sxs-lookup"><span data-stu-id="3f25e-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3f25e-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f25e-105">Description</span></span>  
 <span data-ttu-id="3f25e-106">Se realiza un seguimiento si el Administrador de transacciones local recibe un mensaje Prepared o Replay desde una inscripción volátil de la que ya se ha olvidado.</span><span class="sxs-lookup"><span data-stu-id="3f25e-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3f25e-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="3f25e-107">Troubleshooting</span></span>  
 <span data-ttu-id="3f25e-108">Investigue las causas potenciales de los últimos mensajes que proceden del participante volátil.</span><span class="sxs-lookup"><span data-stu-id="3f25e-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f25e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f25e-109">See also</span></span>

- [<span data-ttu-id="3f25e-110">Traza</span><span class="sxs-lookup"><span data-stu-id="3f25e-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="3f25e-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="3f25e-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3f25e-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3f25e-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
