---
title: Llamadas de seguridad no autorizadas por segundo
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
ms.openlocfilehash: 8aed9f6b8c60c8aecd1b576c13a7063e3a492046
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552510"
---
# <a name="security-calls-not-authorized-per-second"></a><span data-ttu-id="9c9e0-102">Llamadas de seguridad no autorizadas por segundo</span><span class="sxs-lookup"><span data-stu-id="9c9e0-102">Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="9c9e0-103">Nombre del contador: llamadas de seguridad no autorizadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="9c9e0-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9c9e0-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c9e0-104">Description</span></span>  
 <span data-ttu-id="9c9e0-105">El número de llamadas que no pudieron autorizarse en esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="9c9e0-105">Number of calls that failed authorization in this operation in a second.</span></span>  
  
 <span data-ttu-id="9c9e0-106">Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="9c9e0-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="9c9e0-107">Indica que el mensaje entrante es de un usuario válido y que está debidamente protegido, pero dicho usuario no está autorizado a realizar tareas específicas.</span><span class="sxs-lookup"><span data-stu-id="9c9e0-107">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="9c9e0-108">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="9c9e0-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="9c9e0-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="9c9e0-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
