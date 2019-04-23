---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.date: 03/30/2017
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
ms.openlocfilehash: 02e275fa212128c65beda4bc3703949e75ea5092
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220895"
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a><span data-ttu-id="62dcd-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span><span class="sxs-lookup"><span data-stu-id="62dcd-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span></span>
<span data-ttu-id="62dcd-103">Se envió un reintento de mensaje de preparación a un participante sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="62dcd-103">A prepare message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="62dcd-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="62dcd-104">Description</span></span>  
 <span data-ttu-id="62dcd-105">Se le hace un seguimiento si el Administrador de transacciones local necesitara reenviar un Mensaje de preparación a un participante subordinado porque no recibió respuesta en un período determinado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="62dcd-105">Traced if the local Transaction Manager needed to resend a Prepare message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="62dcd-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="62dcd-106">Troubleshooting</span></span>  
 <span data-ttu-id="62dcd-107">Investigue los posibles problemas de red o del producto que impiden la entrega puntual de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="62dcd-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="62dcd-108">Si estos mensajes son frecuentes, puede indicar problemas de infraestructura o tiempos de respuesta anormalmente largos.</span><span class="sxs-lookup"><span data-stu-id="62dcd-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="62dcd-109">Ambos problemas pueden reducir drásticamente el rendimiento de las transacciones dentro del sistema.</span><span class="sxs-lookup"><span data-stu-id="62dcd-109">Both issues can drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62dcd-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="62dcd-110">See also</span></span>

- [<span data-ttu-id="62dcd-111">Traza</span><span class="sxs-lookup"><span data-stu-id="62dcd-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="62dcd-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="62dcd-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="62dcd-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="62dcd-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
