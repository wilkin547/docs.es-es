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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4d7386b2f7c6d78dde41c88c66d216b99cc21050
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="eff9f-102">Mensajes en cola quitados por segundo</span><span class="sxs-lookup"><span data-stu-id="eff9f-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="eff9f-103">Nombre de contador: Mensajes en cola quitados por segundo.</span><span class="sxs-lookup"><span data-stu-id="eff9f-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="eff9f-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="eff9f-104">Description</span></span>  
 <span data-ttu-id="eff9f-105">Número de mensajes quitados cada segundo por el transporte en cola en este servicio.</span><span class="sxs-lookup"><span data-stu-id="eff9f-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="eff9f-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="eff9f-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="eff9f-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="eff9f-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
