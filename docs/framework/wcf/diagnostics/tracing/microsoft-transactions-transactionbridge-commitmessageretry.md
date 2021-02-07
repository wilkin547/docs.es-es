---
description: 'Más información acerca de: Microsoft. Transactions. TransactionBridge. CommitMessageRetry'
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.date: 03/30/2017
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
ms.openlocfilehash: 8f45463ac31c210acd8534df2c4e1ef2922f1c8e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720610"
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a><span data-ttu-id="ba1b1-103">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span><span class="sxs-lookup"><span data-stu-id="ba1b1-103">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span></span>

<span data-ttu-id="ba1b1-104">Se envió un reintento de mensaje de confirmación a un participante sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="ba1b1-104">A commit message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ba1b1-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba1b1-105">Description</span></span>  

 <span data-ttu-id="ba1b1-106">Se le hace un seguimiento si el Administrador de transacciones local necesita reenviar un mensaje de confirmación a un participante subordinado porque no recibió respuesta en un período determinado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="ba1b1-106">Traced if the local Transaction Manager needed to resend a Commit message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ba1b1-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="ba1b1-107">Troubleshooting</span></span>  

 <span data-ttu-id="ba1b1-108">Investigue los posibles problemas de red o del producto que impiden la entrega puntual de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="ba1b1-108">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="ba1b1-109">Si estos mensajes son frecuentes, puede indicar problemas de infraestructura o tiempos de respuesta anormalmente largos.</span><span class="sxs-lookup"><span data-stu-id="ba1b1-109">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="ba1b1-110">Ambos problemas reducirán drásticamente el rendimiento de las transacciones dentro del sistema.</span><span class="sxs-lookup"><span data-stu-id="ba1b1-110">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba1b1-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba1b1-111">See also</span></span>

- [<span data-ttu-id="ba1b1-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="ba1b1-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="ba1b1-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="ba1b1-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ba1b1-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ba1b1-114">Administration and Diagnostics</span></span>](../index.md)
