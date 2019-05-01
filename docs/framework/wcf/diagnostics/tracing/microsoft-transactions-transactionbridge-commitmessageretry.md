---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.date: 03/30/2017
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
ms.openlocfilehash: 3c398aa13a8cd2b87068216d3c07fb29e1a27c3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997971"
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a><span data-ttu-id="3fa0e-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span><span class="sxs-lookup"><span data-stu-id="3fa0e-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span></span>
<span data-ttu-id="3fa0e-103">Se envió un reintento de mensaje de confirmación a un participante sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="3fa0e-103">A commit message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3fa0e-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="3fa0e-104">Description</span></span>  
 <span data-ttu-id="3fa0e-105">Se le hace un seguimiento si el Administrador de transacciones local necesita reenviar un mensaje de confirmación a un participante subordinado porque no recibió respuesta en un período determinado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="3fa0e-105">Traced if the local Transaction Manager needed to resend a Commit message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3fa0e-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="3fa0e-106">Troubleshooting</span></span>  
 <span data-ttu-id="3fa0e-107">Investigue los posibles problemas de red o del producto que impiden la entrega puntual de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="3fa0e-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="3fa0e-108">Si estos mensajes son frecuentes, puede indicar problemas de infraestructura o tiempos de respuesta anormalmente largos.</span><span class="sxs-lookup"><span data-stu-id="3fa0e-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="3fa0e-109">Ambos problemas reducirán drásticamente el rendimiento de las transacciones dentro del sistema.</span><span class="sxs-lookup"><span data-stu-id="3fa0e-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fa0e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fa0e-110">See also</span></span>

- [<span data-ttu-id="3fa0e-111">Traza</span><span class="sxs-lookup"><span data-stu-id="3fa0e-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="3fa0e-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="3fa0e-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3fa0e-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3fa0e-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
