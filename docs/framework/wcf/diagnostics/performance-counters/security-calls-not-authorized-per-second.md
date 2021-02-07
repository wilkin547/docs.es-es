---
description: 'Más información acerca de: llamadas de seguridad no autorizadas por segundo'
title: Llamadas de seguridad no autorizadas por segundo
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
ms.openlocfilehash: 60e1baf2b1ed1f3dc502608e6667266608010f0c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716216"
---
# <a name="security-calls-not-authorized-per-second"></a><span data-ttu-id="76c88-103">Llamadas de seguridad no autorizadas por segundo</span><span class="sxs-lookup"><span data-stu-id="76c88-103">Security Calls Not Authorized Per Second</span></span>

<span data-ttu-id="76c88-104">Nombre del contador: llamadas de seguridad no autorizadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="76c88-104">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="76c88-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="76c88-105">Description</span></span>  

 <span data-ttu-id="76c88-106">El número de llamadas que no pudieron autorizarse en esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="76c88-106">Number of calls that failed authorization in this operation in a second.</span></span>  
  
 <span data-ttu-id="76c88-107">Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="76c88-107">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="76c88-108">Indica que el mensaje entrante es de un usuario válido y que está debidamente protegido, pero dicho usuario no está autorizado a realizar tareas específicas.</span><span class="sxs-lookup"><span data-stu-id="76c88-108">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="76c88-109">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="76c88-109">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="76c88-110">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="76c88-110">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
