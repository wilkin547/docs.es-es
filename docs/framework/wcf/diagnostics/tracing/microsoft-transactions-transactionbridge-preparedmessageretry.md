---
description: 'Más información acerca de: Microsoft. Transactions. TransactionBridge. PreparedMessageRetry'
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.date: 03/30/2017
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
ms.openlocfilehash: 99106493f0eec900875a713b439111fadb150c62
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677280"
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a><span data-ttu-id="946e8-103">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span><span class="sxs-lookup"><span data-stu-id="946e8-103">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span></span>

<span data-ttu-id="946e8-104">Se envió un reintento de mensaje preparado a un coordinador que no responde.</span><span class="sxs-lookup"><span data-stu-id="946e8-104">A prepared message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="946e8-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="946e8-105">Description</span></span>  

 <span data-ttu-id="946e8-106">Se realiza un seguimiento en caso de que el administrador de transacciones local necesite volver a enviar un mensaje de “preparado” a un coordinador superior porque no recibió respuesta transcurrido cierto tiempo.</span><span class="sxs-lookup"><span data-stu-id="946e8-106">Traced if the local Transaction Manager needed to resend a Prepared message to a superior coordinator because it did not receive a response in a given amount of time/</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="946e8-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="946e8-107">Troubleshooting</span></span>  

 <span data-ttu-id="946e8-108">Investigue los posibles problemas de red o del producto que impiden la entrega puntual de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="946e8-108">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="946e8-109">Si estos mensajes son frecuentes, puede indicar problemas de infraestructura o tiempos de respuesta anormalmente largos.</span><span class="sxs-lookup"><span data-stu-id="946e8-109">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="946e8-110">Ambos problemas reducirán drásticamente el rendimiento de las transacciones dentro del sistema.</span><span class="sxs-lookup"><span data-stu-id="946e8-110">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="946e8-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="946e8-111">See also</span></span>

- [<span data-ttu-id="946e8-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="946e8-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="946e8-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="946e8-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="946e8-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="946e8-114">Administration and Diagnostics</span></span>](../index.md)
