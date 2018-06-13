---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 5c1e6c51ffd5aeafe65a67c8989f554ebf0824d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33478922"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="98a19-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="98a19-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>
<span data-ttu-id="98a19-103">La velocidad de mensajes entrantes es demasiado alta.</span><span class="sxs-lookup"><span data-stu-id="98a19-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="98a19-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="98a19-104">Description</span></span>  
 <span data-ttu-id="98a19-105">Este seguimiento se produce cuando se intentan procesar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="98a19-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="98a19-106">No se pudo reenviar un mensaje a un vecino específico porque se ha superado la cuota establecida para dicho vecino.</span><span class="sxs-lookup"><span data-stu-id="98a19-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="98a19-107">Esto se produce cuando un vecino que no responde no borra un trabajo pendiente de mensajes pendientes para ese vecino.</span><span class="sxs-lookup"><span data-stu-id="98a19-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="98a19-108">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="98a19-108">Troubleshooting</span></span>  
 <span data-ttu-id="98a19-109">Reduzca la velocidad a la cual se envían los mensajes dentro de la malla.</span><span class="sxs-lookup"><span data-stu-id="98a19-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98a19-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="98a19-110">See Also</span></span>  
 [<span data-ttu-id="98a19-111">Traza</span><span class="sxs-lookup"><span data-stu-id="98a19-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="98a19-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="98a19-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="98a19-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="98a19-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
