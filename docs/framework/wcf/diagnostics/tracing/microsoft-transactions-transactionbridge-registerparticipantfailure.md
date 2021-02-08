---
description: 'Más información acerca de: Microsoft. Transactions. TransactionBridge. RegisterParticipantFailure'
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: e930ee66720a9f397999d729e8d680fce9a37e29
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99770630"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="1dfa3-103">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="1dfa3-103">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>

<span data-ttu-id="1dfa3-104">El servicio de protocolo WS-AT no pudo registrar a un participante para un protocolo de control.</span><span class="sxs-lookup"><span data-stu-id="1dfa3-104">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1dfa3-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dfa3-105">Description</span></span>  

 <span data-ttu-id="1dfa3-106">Se realiza el seguimiento si MSDTC detecta una solicitud de registro no válida.</span><span class="sxs-lookup"><span data-stu-id="1dfa3-106">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="1dfa3-107">Esto puede deberse a varias solicitudes de registro de realización y errores internos.</span><span class="sxs-lookup"><span data-stu-id="1dfa3-107">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="1dfa3-108">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="1dfa3-108">Troubleshooting</span></span>  

 <span data-ttu-id="1dfa3-109">No intente registrarse para la realización más de una vez.</span><span class="sxs-lookup"><span data-stu-id="1dfa3-109">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="1dfa3-110">Asimismo, inspeccione la cadena de estado dentro del mensaje de seguimiento para determinar si existe cualquier elemento al que se le puede realizar alguna acción.</span><span class="sxs-lookup"><span data-stu-id="1dfa3-110">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dfa3-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1dfa3-111">See also</span></span>

- [<span data-ttu-id="1dfa3-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="1dfa3-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="1dfa3-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="1dfa3-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1dfa3-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1dfa3-114">Administration and Diagnostics</span></span>](../index.md)
