---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: aeeba38eaf674453f4c87cf62f5088c55b5fde2d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290821"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="7a28c-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="7a28c-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>

<span data-ttu-id="7a28c-103">No puede mover o eliminar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="7a28c-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7a28c-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a28c-104">Description</span></span>  

 <span data-ttu-id="7a28c-105">El seguimiento indica que se produjo un error al intentar mover, eliminar o rechazar un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="7a28c-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="7a28c-106">Windows Communication Foundation (WCF) emplean los mensajes de MSMQ (cuando se usan con NetMsmqBinding o MsmqIntegrationBinding). Este seguimiento está relacionado con el valor elegido de la `ReceiveErrorHandling` propiedad en NetMsmqBinding o MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="7a28c-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="7a28c-107">Este seguimiento no indica un error general del sistema.</span><span class="sxs-lookup"><span data-stu-id="7a28c-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="7a28c-108">Sin embargo, indica que la disposición del mensaje dudoso escogida produjo un error en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="7a28c-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="7a28c-109">Para obtener más información sobre cuándo los mensajes son dudosos y cómo configurar el servicio para controlarlos adecuadamente, vea [control de mensajes dudosos](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="7a28c-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a28c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a28c-110">See also</span></span>

- [<span data-ttu-id="7a28c-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="7a28c-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="7a28c-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="7a28c-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="7a28c-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="7a28c-113">Administration and Diagnostics</span></span>](../index.md)
