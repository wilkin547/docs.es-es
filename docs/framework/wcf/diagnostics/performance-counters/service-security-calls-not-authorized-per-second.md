---
title: 'Servicio: Llamadas de seguridad no autorizadas por segundo'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
ms.openlocfilehash: 964eff97a58ab7d5a68dbc1891473ae8d04a50ad
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163883"
---
# <a name="service-security-calls-not-authorized-per-second"></a><span data-ttu-id="3be14-102">Servicio: Llamadas de seguridad no autorizadas por segundo</span><span class="sxs-lookup"><span data-stu-id="3be14-102">Service: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="3be14-103">Nombre de contador: Llamadas de seguridad no autorizadas por segundo</span><span class="sxs-lookup"><span data-stu-id="3be14-103">Counter name: Security Calls Not Authorized Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="3be14-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="3be14-104">Description</span></span>  
 <span data-ttu-id="3be14-105">Número de mensajes entrantes en un segundo, que son de un usuario válido y protegidos correctamente, pero el usuario no está autorizado para realizar tareas específicas.</span><span class="sxs-lookup"><span data-stu-id="3be14-105">Number of incoming messages in one second, which are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="3be14-106">Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="3be14-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="3be14-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="3be14-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="3be14-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="3be14-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
