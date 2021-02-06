---
description: 'Más información acerca de: servicio: llamadas de seguridad no autorizadas por segundo'
title: 'Servicio: Llamadas de seguridad no autorizadas por segundo'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
ms.openlocfilehash: 7203b62a1dd2f01aabd8502c992d357742ddc4e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99635706"
---
# <a name="service-security-calls-not-authorized-per-second"></a><span data-ttu-id="dccef-103">Servicio: Llamadas de seguridad no autorizadas por segundo</span><span class="sxs-lookup"><span data-stu-id="dccef-103">Service: Security Calls Not Authorized Per Second</span></span>

<span data-ttu-id="dccef-104">Nombre de contador: Llamadas de seguridad no autorizadas por segundo</span><span class="sxs-lookup"><span data-stu-id="dccef-104">Counter name: Security Calls Not Authorized Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="dccef-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="dccef-105">Description</span></span>  

 <span data-ttu-id="dccef-106">Número de mensajes entrantes en un segundo, que son de un usuario válido y protegidos correctamente, pero el usuario no está autorizado para realizar tareas específicas.</span><span class="sxs-lookup"><span data-stu-id="dccef-106">Number of incoming messages in one second, which are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="dccef-107">Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="dccef-107">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="dccef-108">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="dccef-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="dccef-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="dccef-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
