---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.date: 03/30/2017
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
ms.openlocfilehash: d5ebe3e1ccce7a85073e2de19d915d116f709b2d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286973"
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a><span data-ttu-id="49e00-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span><span class="sxs-lookup"><span data-stu-id="49e00-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span></span>

<span data-ttu-id="49e00-103">Se envió un reintento de mensaje de preparación a un participante sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="49e00-103">A prepare message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="49e00-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="49e00-104">Description</span></span>  

 <span data-ttu-id="49e00-105">Se le hace un seguimiento si el Administrador de transacciones local necesitara reenviar un Mensaje de preparación a un participante subordinado porque no recibió respuesta en un período determinado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="49e00-105">Traced if the local Transaction Manager needed to resend a Prepare message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="49e00-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="49e00-106">Troubleshooting</span></span>  

 <span data-ttu-id="49e00-107">Investigue los posibles problemas de red o del producto que impiden la entrega puntual de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="49e00-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="49e00-108">Si estos mensajes son frecuentes, puede indicar problemas de infraestructura o tiempos de respuesta anormalmente largos.</span><span class="sxs-lookup"><span data-stu-id="49e00-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="49e00-109">Ambos problemas pueden reducir drásticamente el rendimiento de las transacciones dentro del sistema.</span><span class="sxs-lookup"><span data-stu-id="49e00-109">Both issues can drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49e00-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="49e00-110">See also</span></span>

- [<span data-ttu-id="49e00-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="49e00-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="49e00-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="49e00-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="49e00-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="49e00-113">Administration and Diagnostics</span></span>](../index.md)
