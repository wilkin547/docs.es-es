---
title: Mensajes en cola quitados por segundo
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: 47835086a4ee920e814d9dd6c1e41b9cdc33efec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33471474"
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="a956e-102">Mensajes en cola quitados por segundo</span><span class="sxs-lookup"><span data-stu-id="a956e-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="a956e-103">Nombre de contador: Mensajes en cola quitados por segundo.</span><span class="sxs-lookup"><span data-stu-id="a956e-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a956e-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="a956e-104">Description</span></span>  
 <span data-ttu-id="a956e-105">Número de mensajes quitados cada segundo por el transporte en cola en este servicio.</span><span class="sxs-lookup"><span data-stu-id="a956e-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="a956e-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="a956e-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="a956e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="a956e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
