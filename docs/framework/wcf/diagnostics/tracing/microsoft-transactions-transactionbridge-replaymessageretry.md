---
description: 'Más información acerca de: Microsoft. Transactions. TransactionBridge. ReplayMessageRetry'
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: e4de1416fab2cf7098d0276b6130999c01ea6e3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803261"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a><span data-ttu-id="ee441-103">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span><span class="sxs-lookup"><span data-stu-id="ee441-103">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span></span>

<span data-ttu-id="ee441-104">Se envió un reintento de mensaje de reproducción a un coordinador que no responde.</span><span class="sxs-lookup"><span data-stu-id="ee441-104">A replay message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ee441-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee441-105">Description</span></span>  

 <span data-ttu-id="ee441-106">Se sigue la traza en caso de que el administrador de transacciones local necesite volver a enviar un mensaje de reproducción a un coordinador superior porque no recibió respuesta transcurrido cierto tiempo.</span><span class="sxs-lookup"><span data-stu-id="ee441-106">Traced if the local Transaction Manager needed to resend a Replay message to a superior coordinator because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ee441-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="ee441-107">Troubleshooting</span></span>  

 <span data-ttu-id="ee441-108">Investigue los posibles problemas de red o del producto que impiden la entrega puntual de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="ee441-108">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="ee441-109">Si estos mensajes son frecuentes, puede indicar problemas de infraestructura o tiempos de respuesta anormalmente largos.</span><span class="sxs-lookup"><span data-stu-id="ee441-109">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="ee441-110">Ambos problemas reducirán drásticamente el rendimiento de las transacciones dentro del sistema.</span><span class="sxs-lookup"><span data-stu-id="ee441-110">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee441-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee441-111">See also</span></span>

- [<span data-ttu-id="ee441-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="ee441-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="ee441-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="ee441-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ee441-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ee441-114">Administration and Diagnostics</span></span>](../index.md)
