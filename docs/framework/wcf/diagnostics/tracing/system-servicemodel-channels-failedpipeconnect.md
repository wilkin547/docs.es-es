---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.date: 03/30/2017
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
ms.openlocfilehash: 790a15e5401850f2767cb06f5f321ad80c674f2b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84582418"
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a><span data-ttu-id="45842-102">System.ServiceModel.Channels.FailedPipeConnect</span><span class="sxs-lookup"><span data-stu-id="45842-102">System.ServiceModel.Channels.FailedPipeConnect</span></span>
<span data-ttu-id="45842-103">Se produjo un error al intentar conectar al punto de conexión de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="45842-103">An attempt to connect to the named pipe endpoint failed.</span></span> <span data-ttu-id="45842-104">Se realiza otro intento dentro del período de tiempo de espera especificado.</span><span class="sxs-lookup"><span data-stu-id="45842-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="45842-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="45842-105">Description</span></span>  
 <span data-ttu-id="45842-106">Este seguimiento de traza de información indica un error en la conexión con un punto de conexión de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="45842-106">This informational trace indicates a failure to connect to a named pipe endpoint.</span></span> <span data-ttu-id="45842-107">Esto podría ocurrir si el punto de conexión de canalización con nombre no se encuentra o está ocupado.</span><span class="sxs-lookup"><span data-stu-id="45842-107">This could happen if the named pipe endpoint is not found or is busy.</span></span> <span data-ttu-id="45842-108">Se realizan intentos adicionales, cada uno separado por un espacio de tiempo, hasta que uno se realiza correctamente o finaliza OpenTimeout.</span><span class="sxs-lookup"><span data-stu-id="45842-108">Additional attempts are made, each separated by a short amount of time, until one succeeds or the OpenTimeout expires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45842-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="45842-109">See also</span></span>

- [<span data-ttu-id="45842-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="45842-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="45842-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="45842-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="45842-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="45842-112">Administration and Diagnostics</span></span>](../index.md)
