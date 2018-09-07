---
title: 'punto de conexión: Flujo de transacciones por segundo'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 79f50b6706facd040ec2d325c676f210d5327bf8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44064964"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="44877-102">punto de conexión: Flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="44877-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="44877-103">Nombre del contador: flujo de transacciones por segundo.</span><span class="sxs-lookup"><span data-stu-id="44877-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="44877-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="44877-104">Description</span></span>  
 <span data-ttu-id="44877-105">Número de transacciones de flujo a las operaciones en este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="44877-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="44877-106">Este contador se incrementa siempre que se encuentra un id. de transacción en un mensaje enviado al punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="44877-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="44877-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="44877-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="44877-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="44877-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
