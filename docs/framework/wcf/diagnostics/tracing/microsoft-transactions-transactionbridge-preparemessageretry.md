---
description: 'Más información acerca de: Microsoft. Transactions. TransactionBridge. PrepareMessageRetry'
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.date: 03/30/2017
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
ms.openlocfilehash: 7555336f1082eb097017f9440015f6ab201cdeae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99770786"
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a><span data-ttu-id="d40ad-103">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span><span class="sxs-lookup"><span data-stu-id="d40ad-103">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span></span>

<span data-ttu-id="d40ad-104">Se envió un reintento de mensaje de preparación a un participante sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="d40ad-104">A prepare message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d40ad-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="d40ad-105">Description</span></span>  

 <span data-ttu-id="d40ad-106">Se le hace un seguimiento si el Administrador de transacciones local necesitara reenviar un Mensaje de preparación a un participante subordinado porque no recibió respuesta en un período determinado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="d40ad-106">Traced if the local Transaction Manager needed to resend a Prepare message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d40ad-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="d40ad-107">Troubleshooting</span></span>  

 <span data-ttu-id="d40ad-108">Investigue los posibles problemas de red o del producto que impiden la entrega puntual de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="d40ad-108">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="d40ad-109">Si estos mensajes son frecuentes, puede indicar problemas de infraestructura o tiempos de respuesta anormalmente largos.</span><span class="sxs-lookup"><span data-stu-id="d40ad-109">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="d40ad-110">Ambos problemas pueden reducir drásticamente el rendimiento de las transacciones dentro del sistema.</span><span class="sxs-lookup"><span data-stu-id="d40ad-110">Both issues can drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d40ad-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d40ad-111">See also</span></span>

- [<span data-ttu-id="d40ad-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="d40ad-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="d40ad-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="d40ad-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d40ad-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d40ad-114">Administration and Diagnostics</span></span>](../index.md)
