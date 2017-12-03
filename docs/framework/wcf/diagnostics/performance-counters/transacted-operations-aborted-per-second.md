---
title: "Operaciones de transacción anuladas por segundo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a54b84f2fa0ab9c7531a17e69b10f78c725255ef
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="transacted-operations-aborted-per-second"></a><span data-ttu-id="f9b0a-102">Operaciones de transacción anuladas por segundo</span><span class="sxs-lookup"><span data-stu-id="f9b0a-102">Transacted Operations Aborted Per Second</span></span>
<span data-ttu-id="f9b0a-103">Nombre del contador: operaciones de transacción anuladas por segundo.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-103">Counter Name: Transacted Operations Aborted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f9b0a-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9b0a-104">Description</span></span>  
 <span data-ttu-id="f9b0a-105">Número de operaciones transaccionales anuladas en este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-105">Number of transactional operations that have been aborted in this service in a second.</span></span>  
  
 <span data-ttu-id="f9b0a-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="f9b0a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="f9b0a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="f9b0a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
