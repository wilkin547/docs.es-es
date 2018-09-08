---
title: Llamadas de seguridad no autorizadas por segundo
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4d4970c6f6552163114b33a34ae87c6ed56b5e13
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44195821"
---
# <a name="security-calls-not-authorized-per-second"></a><span data-ttu-id="4c2c7-102">Llamadas de seguridad no autorizadas por segundo</span><span class="sxs-lookup"><span data-stu-id="4c2c7-102">Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="4c2c7-103">Nombre del contador: llamadas de seguridad no autorizadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4c2c7-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c2c7-104">Description</span></span>  
 <span data-ttu-id="4c2c7-105">El número de llamadas que no pudieron autorizarse en esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-105">Number of calls that failed authorization in this operation in a second.</span></span>  
  
 <span data-ttu-id="4c2c7-106">Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="4c2c7-107">Indica que el mensaje entrante es de un usuario válido y que está debidamente protegido, pero dicho usuario no está autorizado a realizar tareas específicas.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-107">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="4c2c7-108">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="4c2c7-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="4c2c7-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="4c2c7-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
