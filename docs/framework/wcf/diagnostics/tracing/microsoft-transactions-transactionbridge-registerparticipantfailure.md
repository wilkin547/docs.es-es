---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: 2f0198d3c288b4c3833cdac8e5f943ba822c22e9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252028"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="7ad4f-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="7ad4f-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>

<span data-ttu-id="7ad4f-103">El servicio de protocolo WS-AT no pudo registrar a un participante para un protocolo de control.</span><span class="sxs-lookup"><span data-stu-id="7ad4f-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7ad4f-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ad4f-104">Description</span></span>  

 <span data-ttu-id="7ad4f-105">Se realiza el seguimiento si MSDTC detecta una solicitud de registro no válida.</span><span class="sxs-lookup"><span data-stu-id="7ad4f-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="7ad4f-106">Esto puede deberse a varias solicitudes de registro de realización y errores internos.</span><span class="sxs-lookup"><span data-stu-id="7ad4f-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="7ad4f-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="7ad4f-107">Troubleshooting</span></span>  

 <span data-ttu-id="7ad4f-108">No intente registrarse para la realización más de una vez.</span><span class="sxs-lookup"><span data-stu-id="7ad4f-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="7ad4f-109">Asimismo, inspeccione la cadena de estado dentro del mensaje de seguimiento para determinar si existe cualquier elemento al que se le puede realizar alguna acción.</span><span class="sxs-lookup"><span data-stu-id="7ad4f-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ad4f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ad4f-110">See also</span></span>

- [<span data-ttu-id="7ad4f-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="7ad4f-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="7ad4f-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="7ad4f-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="7ad4f-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="7ad4f-113">Administration and Diagnostics</span></span>](../index.md)
