---
title: 'punto de conexión: errores en las sesiones de mensajería de confianza por segundo'
ms.date: 03/30/2017
ms.assetid: e9ae808a-7e1f-46b0-9560-d5a866be6d6e
ms.openlocfilehash: f6b48ec4c37c28588dd874a5bfa94a01a2f43b0c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45686146"
---
# <a name="endpoint-reliable-messaging-sessions-faulted-per-second"></a><span data-ttu-id="b0ee6-102">punto de conexión: errores en las sesiones de mensajería de confianza por segundo</span><span class="sxs-lookup"><span data-stu-id="b0ee6-102">Endpoint: Reliable Messaging Sessions Faulted Per Second</span></span>
<span data-ttu-id="b0ee6-103">Nombre de contador: errores en las sesiones de mensajería de confianza por segundo.</span><span class="sxs-lookup"><span data-stu-id="b0ee6-103">Counter Name: Reliable Messaging Sessions Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b0ee6-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0ee6-104">Description</span></span>  
 <span data-ttu-id="b0ee6-105">Número de sesiones de mensajería de confianza fallidas en este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="b0ee6-105">Number of reliable messaging sessions that are faulted at this endpoint in a second.</span></span>  
  
 <span data-ttu-id="b0ee6-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="b0ee6-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b0ee6-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b0ee6-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
