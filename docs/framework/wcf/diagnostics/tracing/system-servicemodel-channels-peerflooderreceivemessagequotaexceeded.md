---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 0ca3d198ce225221348ac7b405ea91ad215cd298
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190904"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="2c9e7-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="2c9e7-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>
<span data-ttu-id="2c9e7-103">La velocidad de mensajes entrantes es demasiado alta.</span><span class="sxs-lookup"><span data-stu-id="2c9e7-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2c9e7-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c9e7-104">Description</span></span>  
 <span data-ttu-id="2c9e7-105">Este seguimiento se produce cuando se intentan procesar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="2c9e7-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="2c9e7-106">No se pudo reenviar un mensaje a un vecino específico porque se ha superado la cuota establecida para dicho vecino.</span><span class="sxs-lookup"><span data-stu-id="2c9e7-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="2c9e7-107">Esto se produce cuando un vecino que no responde no borra un trabajo pendiente de mensajes pendientes para ese vecino.</span><span class="sxs-lookup"><span data-stu-id="2c9e7-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2c9e7-108">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="2c9e7-108">Troubleshooting</span></span>  
 <span data-ttu-id="2c9e7-109">Reduzca la velocidad a la cual se envían los mensajes dentro de la malla.</span><span class="sxs-lookup"><span data-stu-id="2c9e7-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c9e7-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c9e7-110">See also</span></span>

- [<span data-ttu-id="2c9e7-111">Traza</span><span class="sxs-lookup"><span data-stu-id="2c9e7-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="2c9e7-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="2c9e7-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2c9e7-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2c9e7-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
