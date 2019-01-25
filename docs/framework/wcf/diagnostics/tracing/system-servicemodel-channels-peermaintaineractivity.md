---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.date: 03/30/2017
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
ms.openlocfilehash: 4c352ad4ac4ffee5d12c054590ef994bab0ba757
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642586"
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a><span data-ttu-id="1dc10-102">System.ServiceModel.Channels.PeerMaintainerActivity</span><span class="sxs-lookup"><span data-stu-id="1dc10-102">System.ServiceModel.Channels.PeerMaintainerActivity</span></span>
<span data-ttu-id="1dc10-103">El módulo PeerMaintainer realiza una operación específica (los detalles se incluyen en el cuerpo del mensaje de seguimiento).</span><span class="sxs-lookup"><span data-stu-id="1dc10-103">The PeerMaintainer module is performing a specific operation (details contained within the trace message body).</span></span>  
  
## <a name="description"></a><span data-ttu-id="1dc10-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dc10-104">Description</span></span>  
 <span data-ttu-id="1dc10-105">Esta traza se produce durante varias operaciones de PeerMaintainer.</span><span class="sxs-lookup"><span data-stu-id="1dc10-105">This trace occurs during various PeerMaintainer operations.</span></span>  
  
 <span data-ttu-id="1dc10-106">PeerMaintainer es un componente interno de PeerNode.</span><span class="sxs-lookup"><span data-stu-id="1dc10-106">PeerMaintainer is an internal component of PeerNode.</span></span> <span data-ttu-id="1dc10-107">Cada minuto o cada 32 mensajes recibidos, envía un mensaje de LinkUtility a sus vecinos con estadísticas sobre cuántos mensajes se intercambiaron y cuántos son útiles (no duplicados, sin modificar).</span><span class="sxs-lookup"><span data-stu-id="1dc10-107">Every minute, or every 32 messages received, it sends a LinkUtility message to its neighbors with statistics about how many messages are exchanged and how many are useful (non-duplicates, untampered).</span></span> <span data-ttu-id="1dc10-108">Esto ayuda a determinar la utilidad del vínculo de un vecino determinado.</span><span class="sxs-lookup"><span data-stu-id="1dc10-108">This helps determine a particular neighbor's Link Utility.</span></span> <span data-ttu-id="1dc10-109">Aproximadamente cada cinco minutos, el mantenedor comprueba el estado de las conexiones de los vecinos.</span><span class="sxs-lookup"><span data-stu-id="1dc10-109">Approximately every five minutes, the maintainer checks the health of neighbor connections.</span></span> <span data-ttu-id="1dc10-110">Si el número de conexiones de los vecinos supera el número ideal, el mantenedor recorta las conexiones menos útiles.</span><span class="sxs-lookup"><span data-stu-id="1dc10-110">If the number of neighbor connections exceeds the ideal amount, the maintainer prunes off the least useful connections.</span></span> <span data-ttu-id="1dc10-111">Si no hay bastantes conexiones, el mantenedor adquiere conexiones nuevas.</span><span class="sxs-lookup"><span data-stu-id="1dc10-111">If there are not enough connections, the maintainer acquires new connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dc10-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1dc10-112">See also</span></span>
- [<span data-ttu-id="1dc10-113">Traza</span><span class="sxs-lookup"><span data-stu-id="1dc10-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="1dc10-114">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="1dc10-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1dc10-115">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1dc10-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
