---
title: Flujo de transacciones por segundo
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: b47219bd58a9b6c4401baa73177928ddca5b6a8b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254147"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="a54eb-102">Flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="a54eb-102">Transactions Flowed Per Second</span></span>

<span data-ttu-id="a54eb-103">Nombre del contador: flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="a54eb-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="a54eb-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="a54eb-104">Description</span></span>  

 <span data-ttu-id="a54eb-105">Número de transacciones en esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="a54eb-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="a54eb-106">Este contador se incrementa cuando se encuentra presente un id. de transacción en un mensaje enviado a la operación.</span><span class="sxs-lookup"><span data-stu-id="a54eb-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="a54eb-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="a54eb-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="a54eb-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="a54eb-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
