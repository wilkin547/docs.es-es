---
title: "punto de conexión: Llamadas por segundo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aeeedd05c0da46bc210f6f93e6806e3ea72ca862
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint-calls-per-second"></a><span data-ttu-id="27338-102">punto de conexión: Llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="27338-102">Endpoint: Calls Per Second</span></span>
<span data-ttu-id="27338-103">Nombre del contador: llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="27338-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="27338-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="27338-104">Description</span></span>  
 <span data-ttu-id="27338-105">Número de llamadas a este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="27338-105">Number of calls to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="27338-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="27338-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="27338-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="27338-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
