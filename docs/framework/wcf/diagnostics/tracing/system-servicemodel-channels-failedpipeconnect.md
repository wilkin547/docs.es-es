---
description: 'Más información sobre: System. ServiceModel. Channels. FailedPipeConnect'
title: System.ServiceModel.Channels.FailedPipeConnect
ms.date: 03/30/2017
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
ms.openlocfilehash: dbbb3ba2848eaefe70a6d6308daecf84e0a8c7a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99644481"
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a><span data-ttu-id="468f4-103">System.ServiceModel.Channels.FailedPipeConnect</span><span class="sxs-lookup"><span data-stu-id="468f4-103">System.ServiceModel.Channels.FailedPipeConnect</span></span>

<span data-ttu-id="468f4-104">Se produjo un error al intentar conectar al punto de conexión de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="468f4-104">An attempt to connect to the named pipe endpoint failed.</span></span> <span data-ttu-id="468f4-105">Se realiza otro intento dentro del período de tiempo de espera especificado.</span><span class="sxs-lookup"><span data-stu-id="468f4-105">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="468f4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="468f4-106">Description</span></span>  

 <span data-ttu-id="468f4-107">Este seguimiento de traza de información indica un error en la conexión con un punto de conexión de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="468f4-107">This informational trace indicates a failure to connect to a named pipe endpoint.</span></span> <span data-ttu-id="468f4-108">Esto podría ocurrir si el punto de conexión de canalización con nombre no se encuentra o está ocupado.</span><span class="sxs-lookup"><span data-stu-id="468f4-108">This could happen if the named pipe endpoint is not found or is busy.</span></span> <span data-ttu-id="468f4-109">Se realizan intentos adicionales, cada uno separado por un espacio de tiempo, hasta que uno se realiza correctamente o finaliza OpenTimeout.</span><span class="sxs-lookup"><span data-stu-id="468f4-109">Additional attempts are made, each separated by a short amount of time, until one succeeds or the OpenTimeout expires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="468f4-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="468f4-110">See also</span></span>

- [<span data-ttu-id="468f4-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="468f4-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="468f4-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="468f4-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="468f4-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="468f4-113">Administration and Diagnostics</span></span>](../index.md)
