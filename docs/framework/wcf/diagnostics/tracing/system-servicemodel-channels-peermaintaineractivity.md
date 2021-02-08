---
description: 'Más información sobre: System. ServiceModel. Channels. PeerMaintainerActivity'
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.date: 03/30/2017
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
ms.openlocfilehash: da4e4cf87da808cb6779445b6507b51d098132b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780886"
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a><span data-ttu-id="d89e8-103">System.ServiceModel.Channels.PeerMaintainerActivity</span><span class="sxs-lookup"><span data-stu-id="d89e8-103">System.ServiceModel.Channels.PeerMaintainerActivity</span></span>

<span data-ttu-id="d89e8-104">El módulo PeerMaintainer realiza una operación específica (los detalles se incluyen en el cuerpo del mensaje de seguimiento).</span><span class="sxs-lookup"><span data-stu-id="d89e8-104">The PeerMaintainer module is performing a specific operation (details contained within the trace message body).</span></span>  
  
## <a name="description"></a><span data-ttu-id="d89e8-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="d89e8-105">Description</span></span>  

 <span data-ttu-id="d89e8-106">Esta traza se produce durante varias operaciones de PeerMaintainer.</span><span class="sxs-lookup"><span data-stu-id="d89e8-106">This trace occurs during various PeerMaintainer operations.</span></span>  
  
 <span data-ttu-id="d89e8-107">PeerMaintainer es un componente interno de PeerNode.</span><span class="sxs-lookup"><span data-stu-id="d89e8-107">PeerMaintainer is an internal component of PeerNode.</span></span> <span data-ttu-id="d89e8-108">Cada minuto o cada 32 mensajes recibidos, envía un mensaje de LinkUtility a sus vecinos con estadísticas sobre cuántos mensajes se intercambiaron y cuántos son útiles (no duplicados, sin modificar).</span><span class="sxs-lookup"><span data-stu-id="d89e8-108">Every minute, or every 32 messages received, it sends a LinkUtility message to its neighbors with statistics about how many messages are exchanged and how many are useful (non-duplicates, untampered).</span></span> <span data-ttu-id="d89e8-109">Esto ayuda a determinar la utilidad del vínculo de un vecino determinado.</span><span class="sxs-lookup"><span data-stu-id="d89e8-109">This helps determine a particular neighbor's Link Utility.</span></span> <span data-ttu-id="d89e8-110">Aproximadamente cada cinco minutos, el mantenedor comprueba el estado de las conexiones de los vecinos.</span><span class="sxs-lookup"><span data-stu-id="d89e8-110">Approximately every five minutes, the maintainer checks the health of neighbor connections.</span></span> <span data-ttu-id="d89e8-111">Si el número de conexiones de los vecinos supera el número ideal, el mantenedor recorta las conexiones menos útiles.</span><span class="sxs-lookup"><span data-stu-id="d89e8-111">If the number of neighbor connections exceeds the ideal amount, the maintainer prunes off the least useful connections.</span></span> <span data-ttu-id="d89e8-112">Si no hay bastantes conexiones, el mantenedor adquiere conexiones nuevas.</span><span class="sxs-lookup"><span data-stu-id="d89e8-112">If there are not enough connections, the maintainer acquires new connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d89e8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d89e8-113">See also</span></span>

- [<span data-ttu-id="d89e8-114">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="d89e8-114">Tracing</span></span>](index.md)
- [<span data-ttu-id="d89e8-115">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="d89e8-115">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d89e8-116">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d89e8-116">Administration and Diagnostics</span></span>](../index.md)
