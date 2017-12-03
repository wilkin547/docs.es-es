---
title: "punto de conexión: mensajes de mensajería de confianza quitados por segundo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: df6db86febeb88fe934bbd509f6fe8130fd1c811
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="a598b-102">punto de conexión: mensajes de mensajería de confianza quitados por segundo</span><span class="sxs-lookup"><span data-stu-id="a598b-102">Endpoint: Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="a598b-103">Nombre de contador: sesiones de mensajería de confianza quitadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="a598b-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a598b-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="a598b-104">Description</span></span>  
 <span data-ttu-id="a598b-105">Número total de mensajes de mensajería de confianza quitados en este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="a598b-105">Total number of reliable messaging messages that have been dropped at this endpoint in a second.</span></span>  
  
 <span data-ttu-id="a598b-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="a598b-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="a598b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="a598b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
