---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: 1819a269a6775c8541f38f4aa5d733002e3c1e9f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599689"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="3a16a-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="3a16a-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>
<span data-ttu-id="3a16a-103">El servicio de protocolo WS-AT no pudo registrar a un participante para un protocolo de control.</span><span class="sxs-lookup"><span data-stu-id="3a16a-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3a16a-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a16a-104">Description</span></span>  
 <span data-ttu-id="3a16a-105">Se realiza el seguimiento si MSDTC detecta una solicitud de registro no válida.</span><span class="sxs-lookup"><span data-stu-id="3a16a-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="3a16a-106">Esto puede deberse a varias solicitudes de registro de realización y errores internos.</span><span class="sxs-lookup"><span data-stu-id="3a16a-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3a16a-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="3a16a-107">Troubleshooting</span></span>  
 <span data-ttu-id="3a16a-108">No intente registrarse para la realización más de una vez.</span><span class="sxs-lookup"><span data-stu-id="3a16a-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="3a16a-109">Asimismo, inspeccione la cadena de estado dentro del mensaje de seguimiento para determinar si existe cualquier elemento al que se le puede realizar alguna acción.</span><span class="sxs-lookup"><span data-stu-id="3a16a-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a16a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a16a-110">See also</span></span>

- [<span data-ttu-id="3a16a-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="3a16a-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="3a16a-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="3a16a-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3a16a-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3a16a-113">Administration and Diagnostics</span></span>](../index.md)
