---
title: Errores en sesiones de mensajería de confianza por segundo
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: c77d6a5f12dcce15dba94e2f63025a219ebcc6fd
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44077163"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a><span data-ttu-id="209c5-102">Errores en sesiones de mensajería de confianza por segundo</span><span class="sxs-lookup"><span data-stu-id="209c5-102">Reliable Messaging Sessions Faulted Per Second</span></span>
<span data-ttu-id="209c5-103">Nombre de contador: errores en las sesiones de mensajería de confianza por segundo.</span><span class="sxs-lookup"><span data-stu-id="209c5-103">Counter Name: Reliable Messaging Sessions Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="209c5-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="209c5-104">Description</span></span>  
 <span data-ttu-id="209c5-105">Número de sesiones de mensajería confiables que tienen un error en este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="209c5-105">Number of reliable messaging sessions that are faulted in this service in a second.</span></span>  
  
 <span data-ttu-id="209c5-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="209c5-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="209c5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="209c5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
