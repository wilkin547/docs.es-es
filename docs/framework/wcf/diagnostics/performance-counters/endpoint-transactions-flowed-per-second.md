---
title: "punto de conexión: Flujo de transacciones por segundo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 58d1bec0110d669258e8f003cb1e882207133a5d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="b6a9a-102">punto de conexión: Flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="b6a9a-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="b6a9a-103">Nombre del contador: flujo de transacciones por segundo.</span><span class="sxs-lookup"><span data-stu-id="b6a9a-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b6a9a-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6a9a-104">Description</span></span>  
 <span data-ttu-id="b6a9a-105">Número de transacciones de flujo a las operaciones en este extremo en un segundo.</span><span class="sxs-lookup"><span data-stu-id="b6a9a-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="b6a9a-106">Este contador se incrementa siempre que se encuentra un id. de transacción en un mensaje enviado al punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b6a9a-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="b6a9a-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="b6a9a-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b6a9a-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b6a9a-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
