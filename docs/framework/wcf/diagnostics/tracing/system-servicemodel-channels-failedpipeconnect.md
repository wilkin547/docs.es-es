---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d1386d9ac7f58e4dd692bbca3ca3915bc3fe453f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a><span data-ttu-id="65b9b-102">System.ServiceModel.Channels.FailedPipeConnect</span><span class="sxs-lookup"><span data-stu-id="65b9b-102">System.ServiceModel.Channels.FailedPipeConnect</span></span>
<span data-ttu-id="65b9b-103">Se produjo un error al intentar conectar al punto de conexión de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="65b9b-103">An attempt to connect to the named pipe endpoint failed.</span></span> <span data-ttu-id="65b9b-104">Se realiza otro intento dentro del período de tiempo de espera especificado.</span><span class="sxs-lookup"><span data-stu-id="65b9b-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="65b9b-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="65b9b-105">Description</span></span>  
 <span data-ttu-id="65b9b-106">Este seguimiento de traza de información indica un error en la conexión con un extremo de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="65b9b-106">This informational trace indicates a failure to connect to a named pipe endpoint.</span></span> <span data-ttu-id="65b9b-107">Esto podría ocurrir si el extremo de canalización con nombre no se encuentra o está ocupado.</span><span class="sxs-lookup"><span data-stu-id="65b9b-107">This could happen if the named pipe endpoint is not found or is busy.</span></span> <span data-ttu-id="65b9b-108">Se realizan intentos adicionales, cada uno separado por un espacio de tiempo, hasta que uno se realiza correctamente o finaliza OpenTimeout.</span><span class="sxs-lookup"><span data-stu-id="65b9b-108">Additional attempts are made, each separated by a short amount of time, until one succeeds or the OpenTimeout expires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65b9b-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="65b9b-109">See Also</span></span>  
 [<span data-ttu-id="65b9b-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="65b9b-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="65b9b-111">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="65b9b-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="65b9b-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="65b9b-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
