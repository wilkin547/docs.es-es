---
title: Mensajes en cola quitados por segundo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d97d78ddbf52e821cfff2aac08b41e732b189602
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="535db-102">Mensajes en cola quitados por segundo</span><span class="sxs-lookup"><span data-stu-id="535db-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="535db-103">Nombre de contador: Mensajes en cola quitados por segundo.</span><span class="sxs-lookup"><span data-stu-id="535db-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="535db-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="535db-104">Description</span></span>  
 <span data-ttu-id="535db-105">Número de mensajes quitados cada segundo por el transporte en cola en este servicio.</span><span class="sxs-lookup"><span data-stu-id="535db-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="535db-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="535db-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="535db-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="535db-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
