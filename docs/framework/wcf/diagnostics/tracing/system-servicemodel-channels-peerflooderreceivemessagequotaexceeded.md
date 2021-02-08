---
description: 'Más información sobre: System. ServiceModel. Channels. PeerFlooderReceiveMessageQuotaExceeded'
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 8ad164b253491f3a533c4828cd76f915eb5aed68
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780875"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="2e72a-103">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="2e72a-103">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>

<span data-ttu-id="2e72a-104">La velocidad de mensajes entrantes es demasiado alta.</span><span class="sxs-lookup"><span data-stu-id="2e72a-104">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2e72a-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e72a-105">Description</span></span>  

 <span data-ttu-id="2e72a-106">Este seguimiento se produce cuando se intentan procesar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="2e72a-106">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="2e72a-107">No se pudo reenviar un mensaje a un vecino específico porque se ha superado la cuota establecida para dicho vecino.</span><span class="sxs-lookup"><span data-stu-id="2e72a-107">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="2e72a-108">Esto se produce cuando un vecino que no responde no borra un trabajo pendiente de mensajes pendientes para ese vecino.</span><span class="sxs-lookup"><span data-stu-id="2e72a-108">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2e72a-109">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="2e72a-109">Troubleshooting</span></span>  

 <span data-ttu-id="2e72a-110">Reduzca la velocidad a la cual se envían los mensajes dentro de la malla.</span><span class="sxs-lookup"><span data-stu-id="2e72a-110">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e72a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e72a-111">See also</span></span>

- [<span data-ttu-id="2e72a-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="2e72a-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="2e72a-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="2e72a-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2e72a-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2e72a-114">Administration and Diagnostics</span></span>](../index.md)
