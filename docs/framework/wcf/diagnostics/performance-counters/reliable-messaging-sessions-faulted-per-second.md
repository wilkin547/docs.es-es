---
title: "Errores en sesiones de mensajería de confianza por segundo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 23aa57da18072b9c3055079c9d069b282f50c99a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a><span data-ttu-id="0fdca-102">Errores en sesiones de mensajería de confianza por segundo</span><span class="sxs-lookup"><span data-stu-id="0fdca-102">Reliable Messaging Sessions Faulted Per Second</span></span>
<span data-ttu-id="0fdca-103">Nombre de contador: errores en las sesiones de mensajería de confianza por segundo.</span><span class="sxs-lookup"><span data-stu-id="0fdca-103">Counter Name: Reliable Messaging Sessions Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0fdca-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="0fdca-104">Description</span></span>  
 <span data-ttu-id="0fdca-105">Número de sesiones de mensajería confiables que tienen un error en este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="0fdca-105">Number of reliable messaging sessions that are faulted in this service in a second.</span></span>  
  
 <span data-ttu-id="0fdca-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="0fdca-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="0fdca-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="0fdca-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
