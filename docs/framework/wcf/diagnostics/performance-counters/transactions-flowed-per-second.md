---
title: Flujo de transacciones por segundo
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: 8b6077af3f98f7a205772b4883dc122374083e00
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163831"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="f7069-102">Flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="f7069-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="f7069-103">Nombre del contador: flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="f7069-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="f7069-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7069-104">Description</span></span>  
 <span data-ttu-id="f7069-105">Número de transacciones en esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="f7069-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="f7069-106">Este contador se incrementa cuando se encuentra presente un id. de transacción en un mensaje enviado a la operación.</span><span class="sxs-lookup"><span data-stu-id="f7069-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="f7069-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="f7069-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="f7069-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="f7069-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
