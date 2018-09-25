---
title: 'punto de conexión: Llamadas de seguridad no autorizadas por segundo'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
author: BrucePerlerMS
ms.openlocfilehash: 4abea795eb196d339beec17fa7a171927aa85324
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47078375"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a><span data-ttu-id="3452b-102">punto de conexión: Llamadas de seguridad no autorizadas por segundo</span><span class="sxs-lookup"><span data-stu-id="3452b-102">Endpoint: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="3452b-103">Nombre del contador: llamadas de seguridad no autorizadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="3452b-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3452b-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="3452b-104">Description</span></span>  
 <span data-ttu-id="3452b-105">Número de mensajes entrantes en un segundo, que son de un usuario válido y protegidos correctamente, pero el usuario no está autorizado para realizar tareas específicas.</span><span class="sxs-lookup"><span data-stu-id="3452b-105">Number of incoming messages in a second that are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="3452b-106">Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="3452b-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="3452b-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="3452b-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="3452b-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="3452b-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
