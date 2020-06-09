---
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: 162452d5d12859571d78ef19cf1d838953ee7acd
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596212"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a><span data-ttu-id="a4c0e-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span><span class="sxs-lookup"><span data-stu-id="a4c0e-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span></span>
<span data-ttu-id="a4c0e-103">Se envió un reintento de mensaje de reproducción a un coordinador que no responde.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-103">A replay message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a4c0e-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4c0e-104">Description</span></span>  
 <span data-ttu-id="a4c0e-105">Se sigue la traza en caso de que el administrador de transacciones local necesite volver a enviar un mensaje de reproducción a un coordinador superior porque no recibió respuesta transcurrido cierto tiempo.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-105">Traced if the local Transaction Manager needed to resend a Replay message to a superior coordinator because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="a4c0e-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="a4c0e-106">Troubleshooting</span></span>  
 <span data-ttu-id="a4c0e-107">Investigue los posibles problemas de red o del producto que impiden la entrega puntual de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="a4c0e-108">Si estos mensajes son frecuentes, puede indicar problemas de infraestructura o tiempos de respuesta anormalmente largos.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="a4c0e-109">Ambos problemas reducirán drásticamente el rendimiento de las transacciones dentro del sistema.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4c0e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4c0e-110">See also</span></span>

- [<span data-ttu-id="a4c0e-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="a4c0e-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="a4c0e-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="a4c0e-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="a4c0e-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="a4c0e-113">Administration and Diagnostics</span></span>](../index.md)
