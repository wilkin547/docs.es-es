---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: f89dd1373d67714046f8cb958582c3a5dea04456
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674787"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="106eb-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="106eb-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="106eb-103">No puede mover o eliminar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="106eb-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="106eb-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="106eb-104">Description</span></span>  
 <span data-ttu-id="106eb-105">El seguimiento indica que se produjo un error al intentar mover, eliminar o rechazar un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="106eb-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="106eb-106">Los mensajes MSMQ son empleados por Windows Communication Foundation (WCF) (cuando se utilizan con NetMsmqBinding o MsmqIntegrationBinding). Este seguimiento está relacionado con `ReceiveErrorHandling` el valor elegido de la propiedad en NetMsmqBinding o MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="106eb-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="106eb-107">Este seguimiento no indica un error general del sistema.</span><span class="sxs-lookup"><span data-stu-id="106eb-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="106eb-108">Sin embargo, indica que la disposición del mensaje dudoso escogida produjo un error en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="106eb-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="106eb-109">Para obtener más información sobre cuándo los mensajes se vuelven dudosos y cómo configurar el servicio para que los controle adecuadamente, vea [Manejo de mensajes envenenados](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="106eb-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="106eb-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="106eb-110">See also</span></span>

- [<span data-ttu-id="106eb-111">Rastreo</span><span class="sxs-lookup"><span data-stu-id="106eb-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="106eb-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="106eb-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="106eb-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="106eb-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
