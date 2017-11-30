---
title: "Operaciones de transacción dudosas por segundo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7d42046d2d636d507aa682c349f29dcecedca657
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="transacted-operations-in-doubt-per-second"></a><span data-ttu-id="5eb8f-102">Operaciones de transacción dudosas por segundo</span><span class="sxs-lookup"><span data-stu-id="5eb8f-102">Transacted Operations In Doubt Per Second</span></span>
<span data-ttu-id="5eb8f-103">Nombre del contador: Operaciones de transacción en duda por segundo.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-103">Counter Name: Transacted Operations In Doubt Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5eb8f-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="5eb8f-104">Description</span></span>  
 <span data-ttu-id="5eb8f-105">El número de operaciones de transacción con un resultado en duda en este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-105">Number of transactional operations with an in-doubt outcome in this service in a second.</span></span>  
  
 <span data-ttu-id="5eb8f-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="5eb8f-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="5eb8f-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="5eb8f-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
