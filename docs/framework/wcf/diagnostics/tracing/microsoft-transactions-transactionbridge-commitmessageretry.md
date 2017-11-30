---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: be874cc0b3fb15f80bb5cd6b97174b515703385c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a><span data-ttu-id="14fba-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span><span class="sxs-lookup"><span data-stu-id="14fba-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span></span>
<span data-ttu-id="14fba-103">Se envió un reintento de mensaje de confirmación a un participante sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="14fba-103">A commit message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="14fba-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="14fba-104">Description</span></span>  
 <span data-ttu-id="14fba-105">Se le hace un seguimiento si el Administrador de transacciones local necesita reenviar un mensaje de confirmación a un participante subordinado porque no recibió respuesta en un período determinado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="14fba-105">Traced if the local Transaction Manager needed to resend a Commit message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="14fba-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="14fba-106">Troubleshooting</span></span>  
 <span data-ttu-id="14fba-107">Investigue los posibles problemas de red o del producto que impiden la entrega puntual de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="14fba-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="14fba-108">Si estos mensajes son frecuentes, puede indicar problemas de infraestructura o tiempos de respuesta anormalmente largos.</span><span class="sxs-lookup"><span data-stu-id="14fba-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="14fba-109">Ambos problemas reducirán drásticamente el rendimiento de las transacciones dentro del sistema.</span><span class="sxs-lookup"><span data-stu-id="14fba-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14fba-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="14fba-110">See Also</span></span>  
 [<span data-ttu-id="14fba-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="14fba-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="14fba-112">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="14fba-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="14fba-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="14fba-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
