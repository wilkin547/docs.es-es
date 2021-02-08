---
description: 'Más información sobre: System. ServiceModel. Channels. MsmqMessageRejected'
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 4400519c814627fd2a2f2585359d6d6376798ac0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780952"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="b13aa-103">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="b13aa-103">System.ServiceModel.Channels.MsmqMessageRejected</span></span>

<span data-ttu-id="b13aa-104">MSMQ rechazó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b13aa-104">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b13aa-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="b13aa-105">Description</span></span>  

 <span data-ttu-id="b13aa-106">Este seguimiento indica que se rechazó un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="b13aa-106">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="b13aa-107">Los mensajes de MSMQ se pueden rechazar cuando Windows Communication Foundation (WCF) (que se usa con NetMsmqBinding o MsmqIntegrationBinding) no puede procesarlos.</span><span class="sxs-lookup"><span data-stu-id="b13aa-107">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="b13aa-108">Tales mensajes se conocen como mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="b13aa-108">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="b13aa-109">Se rechaza un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida en `Reject`.</span><span class="sxs-lookup"><span data-stu-id="b13aa-109">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="b13aa-110">Un mensaje rechazado se devuelve a la cola de mensajes con [problemas de entrega](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)del remitente.</span><span class="sxs-lookup"><span data-stu-id="b13aa-110">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="b13aa-111">Para obtener más información sobre cuándo los mensajes son dudosos y cómo configurar el servicio para controlarlos adecuadamente, vea [control de mensajes dudosos](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="b13aa-111">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
 <span data-ttu-id="b13aa-112">Para obtener más información sobre lo que significa un mensaje rechazado en MSMQ, vea [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="b13aa-112">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b13aa-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b13aa-113">See also</span></span>

- [<span data-ttu-id="b13aa-114">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="b13aa-114">Tracing</span></span>](index.md)
- [<span data-ttu-id="b13aa-115">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="b13aa-115">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b13aa-116">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b13aa-116">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="b13aa-117">Administración de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="b13aa-117">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="b13aa-118">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="b13aa-118">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span></span>
