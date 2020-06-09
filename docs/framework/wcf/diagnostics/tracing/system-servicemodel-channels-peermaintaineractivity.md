---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.date: 03/30/2017
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
ms.openlocfilehash: ce97eaa2ad5c9dbd5f4d6f81186960c489eb4b85
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596082"
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a><span data-ttu-id="d0318-102">System.ServiceModel.Channels.PeerMaintainerActivity</span><span class="sxs-lookup"><span data-stu-id="d0318-102">System.ServiceModel.Channels.PeerMaintainerActivity</span></span>
<span data-ttu-id="d0318-103">El módulo PeerMaintainer realiza una operación específica (los detalles se incluyen en el cuerpo del mensaje de seguimiento).</span><span class="sxs-lookup"><span data-stu-id="d0318-103">The PeerMaintainer module is performing a specific operation (details contained within the trace message body).</span></span>  
  
## <a name="description"></a><span data-ttu-id="d0318-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0318-104">Description</span></span>  
 <span data-ttu-id="d0318-105">Esta traza se produce durante varias operaciones de PeerMaintainer.</span><span class="sxs-lookup"><span data-stu-id="d0318-105">This trace occurs during various PeerMaintainer operations.</span></span>  
  
 <span data-ttu-id="d0318-106">PeerMaintainer es un componente interno de PeerNode.</span><span class="sxs-lookup"><span data-stu-id="d0318-106">PeerMaintainer is an internal component of PeerNode.</span></span> <span data-ttu-id="d0318-107">Cada minuto o cada 32 mensajes recibidos, envía un mensaje de LinkUtility a sus vecinos con estadísticas sobre cuántos mensajes se intercambiaron y cuántos son útiles (no duplicados, sin modificar).</span><span class="sxs-lookup"><span data-stu-id="d0318-107">Every minute, or every 32 messages received, it sends a LinkUtility message to its neighbors with statistics about how many messages are exchanged and how many are useful (non-duplicates, untampered).</span></span> <span data-ttu-id="d0318-108">Esto ayuda a determinar la utilidad del vínculo de un vecino determinado.</span><span class="sxs-lookup"><span data-stu-id="d0318-108">This helps determine a particular neighbor's Link Utility.</span></span> <span data-ttu-id="d0318-109">Aproximadamente cada cinco minutos, el mantenedor comprueba el estado de las conexiones de los vecinos.</span><span class="sxs-lookup"><span data-stu-id="d0318-109">Approximately every five minutes, the maintainer checks the health of neighbor connections.</span></span> <span data-ttu-id="d0318-110">Si el número de conexiones de los vecinos supera el número ideal, el mantenedor recorta las conexiones menos útiles.</span><span class="sxs-lookup"><span data-stu-id="d0318-110">If the number of neighbor connections exceeds the ideal amount, the maintainer prunes off the least useful connections.</span></span> <span data-ttu-id="d0318-111">Si no hay bastantes conexiones, el mantenedor adquiere conexiones nuevas.</span><span class="sxs-lookup"><span data-stu-id="d0318-111">If there are not enough connections, the maintainer acquires new connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0318-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0318-112">See also</span></span>

- [<span data-ttu-id="d0318-113">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="d0318-113">Tracing</span></span>](index.md)
- [<span data-ttu-id="d0318-114">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="d0318-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d0318-115">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d0318-115">Administration and Diagnostics</span></span>](../index.md)
