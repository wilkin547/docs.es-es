---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.date: 03/30/2017
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
ms.openlocfilehash: 472821d880433cd6a3292838a48bcb0b5bb34c43
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152300"
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a><span data-ttu-id="7d7a3-102">System.ServiceModel.Channels.FailedPipeConnect</span><span class="sxs-lookup"><span data-stu-id="7d7a3-102">System.ServiceModel.Channels.FailedPipeConnect</span></span>
<span data-ttu-id="7d7a3-103">Se produjo un error al intentar conectar al punto de conexión de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="7d7a3-103">An attempt to connect to the named pipe endpoint failed.</span></span> <span data-ttu-id="7d7a3-104">Se realiza otro intento dentro del período de tiempo de espera especificado.</span><span class="sxs-lookup"><span data-stu-id="7d7a3-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7d7a3-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d7a3-105">Description</span></span>  
 <span data-ttu-id="7d7a3-106">Este seguimiento de traza de información indica un error en la conexión con un punto de conexión de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="7d7a3-106">This informational trace indicates a failure to connect to a named pipe endpoint.</span></span> <span data-ttu-id="7d7a3-107">Esto podría ocurrir si el punto de conexión de canalización con nombre no se encuentra o está ocupado.</span><span class="sxs-lookup"><span data-stu-id="7d7a3-107">This could happen if the named pipe endpoint is not found or is busy.</span></span> <span data-ttu-id="7d7a3-108">Se realizan intentos adicionales, cada uno separado por un espacio de tiempo, hasta que uno se realiza correctamente o finaliza OpenTimeout.</span><span class="sxs-lookup"><span data-stu-id="7d7a3-108">Additional attempts are made, each separated by a short amount of time, until one succeeds or the OpenTimeout expires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d7a3-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d7a3-109">See also</span></span>

- [<span data-ttu-id="7d7a3-110">Traza</span><span class="sxs-lookup"><span data-stu-id="7d7a3-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="7d7a3-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="7d7a3-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="7d7a3-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="7d7a3-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
