---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 339ba8df7e782281fcec962ff6c6f01988122b3a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a><span data-ttu-id="ac07e-102">System.ServiceModel.Channels.FailedAcceptFromPool</span><span class="sxs-lookup"><span data-stu-id="ac07e-102">System.ServiceModel.Channels.FailedAcceptFromPool</span></span>
<span data-ttu-id="ac07e-103">Error en un intento para usar de nuevo una conexión agrupada.</span><span class="sxs-lookup"><span data-stu-id="ac07e-103">An attempt to reuse a pooled connection failed.</span></span> <span data-ttu-id="ac07e-104">Se realiza otro intento dentro del período de tiempo de espera especificado.</span><span class="sxs-lookup"><span data-stu-id="ac07e-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ac07e-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac07e-105">Description</span></span>  
 <span data-ttu-id="ac07e-106">Este seguimiento de información indica que se ha producido un error mientras se intentaba reutilizar una conexión de grupo.</span><span class="sxs-lookup"><span data-stu-id="ac07e-106">This informational trace indicates that an error has occurred while attempting to reuse a pooled connection.</span></span> <span data-ttu-id="ac07e-107">Esto podría haber pasado porque la conexión de grupo no era compatible, no estaba preparada o estaba aún activa.</span><span class="sxs-lookup"><span data-stu-id="ac07e-107">This could happen because the pooled connection was not compatible, ready, or still active.</span></span> <span data-ttu-id="ac07e-108">Hay un tiempo establecido para realizar intentos adicionales de reutilizar otra conexión de grupo, y en caso de que no se encuentren conexiones utilizables, se crea una nueva.</span><span class="sxs-lookup"><span data-stu-id="ac07e-108">Additional attempts to reuse other pooled connection are made within a given timeout and a new connection is created in case no usable connections are found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac07e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac07e-109">See Also</span></span>  
 [<span data-ttu-id="ac07e-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="ac07e-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="ac07e-111">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="ac07e-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="ac07e-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ac07e-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
