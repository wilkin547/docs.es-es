---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: 7e7bd48d206456af6a5a8662516c4d9c82b3ed2f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47196907"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="0a0fe-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="0a0fe-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="0a0fe-103">No puede mover o eliminar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0a0fe-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0a0fe-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="0a0fe-104">Description</span></span>  
 <span data-ttu-id="0a0fe-105">El seguimiento indica que se produjo un error al intentar mover, eliminar o rechazar un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="0a0fe-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="0a0fe-106">Los mensajes de MSMQ se emplean por Windows Communication Foundation (WCF) (cuando se utiliza con NetMsmqBinding o MsmqIntegrationBinding). Este seguimiento está relacionado con el valor elegido de la `ReceiveErrorHandling` propiedad en NetMsmqBinding o MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="0a0fe-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="0a0fe-107">Este seguimiento no indica un error general del sistema.</span><span class="sxs-lookup"><span data-stu-id="0a0fe-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="0a0fe-108">Sin embargo, indica que la disposición del mensaje dudoso escogida produjo un error en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="0a0fe-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="0a0fe-109">Consulte [de mensajes dudosos](https://go.microsoft.com/fwlink/?LinkID=99546) para obtener más detalles sobre cuándo los mensajes en dudosos y cómo configurar el servicio para controlarlos adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="0a0fe-109">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a0fe-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a0fe-110">See Also</span></span>  
 [<span data-ttu-id="0a0fe-111">Traza</span><span class="sxs-lookup"><span data-stu-id="0a0fe-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="0a0fe-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="0a0fe-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="0a0fe-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="0a0fe-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
