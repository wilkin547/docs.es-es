---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: b94c017f6ed3a76a6bc5ed2cb970877ad18ef9ea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610427"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="1e320-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="1e320-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>
<span data-ttu-id="1e320-103">El servicio de protocolo WS-AT no pudo registrar a un participante para un protocolo de control.</span><span class="sxs-lookup"><span data-stu-id="1e320-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1e320-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e320-104">Description</span></span>  
 <span data-ttu-id="1e320-105">Se realiza el seguimiento si MSDTC detecta una solicitud de registro no válida.</span><span class="sxs-lookup"><span data-stu-id="1e320-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="1e320-106">Esto puede deberse a varias solicitudes de registro de realización y errores internos.</span><span class="sxs-lookup"><span data-stu-id="1e320-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="1e320-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="1e320-107">Troubleshooting</span></span>  
 <span data-ttu-id="1e320-108">No intente registrarse para la realización más de una vez.</span><span class="sxs-lookup"><span data-stu-id="1e320-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="1e320-109">Asimismo, inspeccione la cadena de estado dentro del mensaje de seguimiento para determinar si existe cualquier elemento al que se le puede realizar alguna acción.</span><span class="sxs-lookup"><span data-stu-id="1e320-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e320-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e320-110">See also</span></span>
- [<span data-ttu-id="1e320-111">Traza</span><span class="sxs-lookup"><span data-stu-id="1e320-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="1e320-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="1e320-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1e320-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1e320-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
