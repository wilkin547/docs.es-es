---
title: Flujo de transacciones por segundo
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: e77aef4cfff1e64f112e720183675dfb7aa25d27
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392941"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="b0bd0-102">Flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="b0bd0-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="b0bd0-103">Nombre del contador: flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="b0bd0-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="b0bd0-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0bd0-104">Description</span></span>  
 <span data-ttu-id="b0bd0-105">Número de transacciones en esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="b0bd0-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="b0bd0-106">Este contador se incrementa cuando se encuentra presente un id. de transacción en un mensaje enviado a la operación.</span><span class="sxs-lookup"><span data-stu-id="b0bd0-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="b0bd0-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="b0bd0-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b0bd0-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b0bd0-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
