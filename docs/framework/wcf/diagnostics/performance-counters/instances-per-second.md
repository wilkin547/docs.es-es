---
title: Instancias por segundo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74579397-1058-4278-80cf-2d00854a480f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 40eb52dcc196f4c4a89508246af1c129b5eadb8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="instances-per-second"></a><span data-ttu-id="3c6d9-102">Instancias por segundo</span><span class="sxs-lookup"><span data-stu-id="3c6d9-102">Instances Per Second</span></span>
<span data-ttu-id="3c6d9-103">Nombre de contador: Instancias creadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="3c6d9-103">Counter Name: Instances Created Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3c6d9-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c6d9-104">Description</span></span>  
 <span data-ttu-id="3c6d9-105">Número de instancias del servicio creadas en un segundo.</span><span class="sxs-lookup"><span data-stu-id="3c6d9-105">Total number of service instances created in a second.</span></span>  
  
 <span data-ttu-id="3c6d9-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="3c6d9-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="3c6d9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="3c6d9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
