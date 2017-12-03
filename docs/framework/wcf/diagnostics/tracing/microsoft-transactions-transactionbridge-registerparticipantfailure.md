---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 16b0261a53df29b1fc2049c25375c651735a524c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="247b2-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="247b2-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>
<span data-ttu-id="247b2-103">El servicio de protocolo WS-AT no pudo registrar a un participante para un protocolo de control.</span><span class="sxs-lookup"><span data-stu-id="247b2-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="247b2-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="247b2-104">Description</span></span>  
 <span data-ttu-id="247b2-105">Se realiza el seguimiento si MSDTC detecta una solicitud de registro no válida.</span><span class="sxs-lookup"><span data-stu-id="247b2-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="247b2-106">Esto puede deberse a varias solicitudes de registro de realización y errores internos.</span><span class="sxs-lookup"><span data-stu-id="247b2-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="247b2-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="247b2-107">Troubleshooting</span></span>  
 <span data-ttu-id="247b2-108">No intente registrarse para la realización más de una vez.</span><span class="sxs-lookup"><span data-stu-id="247b2-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="247b2-109">Asimismo, inspeccione la cadena de estado dentro del mensaje de seguimiento para determinar si existe cualquier elemento al que se le puede realizar alguna acción.</span><span class="sxs-lookup"><span data-stu-id="247b2-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="247b2-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="247b2-110">See Also</span></span>  
 [<span data-ttu-id="247b2-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="247b2-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="247b2-112">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="247b2-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="247b2-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="247b2-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
