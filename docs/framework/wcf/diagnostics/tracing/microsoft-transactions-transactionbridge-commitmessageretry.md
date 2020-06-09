---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.date: 03/30/2017
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
ms.openlocfilehash: f37bc252e12aef94d77c0745d36b5c8232a169eb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599742"
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a><span data-ttu-id="cec23-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span><span class="sxs-lookup"><span data-stu-id="cec23-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span></span>
<span data-ttu-id="cec23-103">Se envió un reintento de mensaje de confirmación a un participante sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="cec23-103">A commit message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cec23-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="cec23-104">Description</span></span>  
 <span data-ttu-id="cec23-105">Se le hace un seguimiento si el Administrador de transacciones local necesita reenviar un mensaje de confirmación a un participante subordinado porque no recibió respuesta en un período determinado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="cec23-105">Traced if the local Transaction Manager needed to resend a Commit message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="cec23-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="cec23-106">Troubleshooting</span></span>  
 <span data-ttu-id="cec23-107">Investigue los posibles problemas de red o del producto que impiden la entrega puntual de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="cec23-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="cec23-108">Si estos mensajes son frecuentes, puede indicar problemas de infraestructura o tiempos de respuesta anormalmente largos.</span><span class="sxs-lookup"><span data-stu-id="cec23-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="cec23-109">Ambos problemas reducirán drásticamente el rendimiento de las transacciones dentro del sistema.</span><span class="sxs-lookup"><span data-stu-id="cec23-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec23-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="cec23-110">See also</span></span>

- [<span data-ttu-id="cec23-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="cec23-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="cec23-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="cec23-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="cec23-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="cec23-113">Administration and Diagnostics</span></span>](../index.md)
