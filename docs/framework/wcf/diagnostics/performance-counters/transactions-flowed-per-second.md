---
description: 'Más información acerca de: flujo de transacciones por segundo'
title: Flujo de transacciones por segundo
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: f37c79e89efb8a013719f44350772919b7222a61
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771007"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="04315-103">Flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="04315-103">Transactions Flowed Per Second</span></span>

<span data-ttu-id="04315-104">Nombre del contador: flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="04315-104">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="04315-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="04315-105">Description</span></span>  

 <span data-ttu-id="04315-106">Número de transacciones en esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="04315-106">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="04315-107">Este contador se incrementa cuando se encuentra presente un id. de transacción en un mensaje enviado a la operación.</span><span class="sxs-lookup"><span data-stu-id="04315-107">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="04315-108">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="04315-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="04315-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="04315-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
