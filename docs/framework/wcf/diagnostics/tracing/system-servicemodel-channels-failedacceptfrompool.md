---
description: 'Más información sobre: System. ServiceModel. Channels. FailedAcceptFromPool'
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.date: 03/30/2017
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
ms.openlocfilehash: 1b3c15594611726fd4872197b97ad4ed56c085c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99635264"
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a><span data-ttu-id="7a508-103">System.ServiceModel.Channels.FailedAcceptFromPool</span><span class="sxs-lookup"><span data-stu-id="7a508-103">System.ServiceModel.Channels.FailedAcceptFromPool</span></span>

<span data-ttu-id="7a508-104">Error en un intento para usar de nuevo una conexión agrupada.</span><span class="sxs-lookup"><span data-stu-id="7a508-104">An attempt to reuse a pooled connection failed.</span></span> <span data-ttu-id="7a508-105">Se realiza otro intento dentro del período de tiempo de espera especificado.</span><span class="sxs-lookup"><span data-stu-id="7a508-105">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7a508-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a508-106">Description</span></span>  

 <span data-ttu-id="7a508-107">Este seguimiento de información indica que se ha producido un error mientras se intentaba reutilizar una conexión de grupo.</span><span class="sxs-lookup"><span data-stu-id="7a508-107">This informational trace indicates that an error has occurred while attempting to reuse a pooled connection.</span></span> <span data-ttu-id="7a508-108">Esto podría haber pasado porque la conexión de grupo no era compatible, no estaba preparada o estaba aún activa.</span><span class="sxs-lookup"><span data-stu-id="7a508-108">This could happen because the pooled connection was not compatible, ready, or still active.</span></span> <span data-ttu-id="7a508-109">Hay un tiempo establecido para realizar intentos adicionales de reutilizar otra conexión de grupo, y en caso de que no se encuentren conexiones utilizables, se crea una nueva.</span><span class="sxs-lookup"><span data-stu-id="7a508-109">Additional attempts to reuse other pooled connection are made within a given timeout and a new connection is created in case no usable connections are found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a508-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a508-110">See also</span></span>

- [<span data-ttu-id="7a508-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="7a508-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="7a508-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="7a508-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="7a508-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="7a508-113">Administration and Diagnostics</span></span>](../index.md)
