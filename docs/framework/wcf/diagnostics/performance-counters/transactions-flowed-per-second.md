---
title: Flujo de transacciones por segundo
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: a71095b9fdd16d7e220be8a0aeb0a746bb50527e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33472923"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="8f4bc-102">Flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="8f4bc-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="8f4bc-103">Nombre del contador: flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="8f4bc-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="8f4bc-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f4bc-104">Description</span></span>  
 <span data-ttu-id="8f4bc-105">Número de transacciones en esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="8f4bc-106">Este contador se incrementa cuando se encuentra presente un id. de transacción en un mensaje enviado a la operación.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="8f4bc-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="8f4bc-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="8f4bc-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
