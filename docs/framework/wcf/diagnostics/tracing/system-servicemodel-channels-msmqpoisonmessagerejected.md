---
description: 'Más información sobre: System. ServiceModel. Channels. MsmqPoisonMessageRejected'
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 856c28dd313867de0661d4950dd67e6740e2b338
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759307"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="3393c-103">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="3393c-103">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>

<span data-ttu-id="3393c-104">Mensaje dudoso rechazado.</span><span class="sxs-lookup"><span data-stu-id="3393c-104">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3393c-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="3393c-105">Description</span></span>  

 <span data-ttu-id="3393c-106">El seguimiento de traza indica que se encontró un mensaje dudoso y fue posteriormente rechazado.</span><span class="sxs-lookup"><span data-stu-id="3393c-106">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="3393c-107">Esto sucede cuando la propiedad `ReceiveErrorHandling` en NetMsmqBinding o MsmqIntegrationBinding está establecida en `Reject`.</span><span class="sxs-lookup"><span data-stu-id="3393c-107">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="3393c-108">Un mensaje rechazado se devuelve a la cola de mensajes con [problemas de entrega](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)del remitente.</span><span class="sxs-lookup"><span data-stu-id="3393c-108">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="3393c-109">Para obtener más información sobre cuándo los mensajes son dudosos y cómo configurar el servicio para controlarlos adecuadamente, vea [control de mensajes dudosos](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="3393c-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="3393c-110">Para obtener más información sobre lo que significa un mensaje rechazado en MSMQ, vea [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="3393c-110">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3393c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3393c-111">See also</span></span>

- [<span data-ttu-id="3393c-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="3393c-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="3393c-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="3393c-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3393c-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3393c-114">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="3393c-115">Administración de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="3393c-115">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="3393c-116">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="3393c-116">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span></span>
