---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 12978af11ac3663403deaeb21818643ca2d366aa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260362"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="e371e-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="e371e-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>

<span data-ttu-id="e371e-103">MSMQ rechazó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e371e-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e371e-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="e371e-104">Description</span></span>  

 <span data-ttu-id="e371e-105">Este seguimiento indica que se rechazó un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e371e-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="e371e-106">Los mensajes de MSMQ se pueden rechazar cuando Windows Communication Foundation (WCF) (que se usa con NetMsmqBinding o MsmqIntegrationBinding) no puede procesarlos.</span><span class="sxs-lookup"><span data-stu-id="e371e-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="e371e-107">Tales mensajes se conocen como mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="e371e-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="e371e-108">Se rechaza un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida en `Reject`.</span><span class="sxs-lookup"><span data-stu-id="e371e-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="e371e-109">Un mensaje rechazado se devuelve a la cola de mensajes con [problemas de entrega](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)del remitente.</span><span class="sxs-lookup"><span data-stu-id="e371e-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="e371e-110">Para obtener más información sobre cuándo los mensajes son dudosos y cómo configurar el servicio para controlarlos adecuadamente, vea [control de mensajes dudosos](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="e371e-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
 <span data-ttu-id="e371e-111">Para obtener más información sobre lo que significa un mensaje rechazado en MSMQ, vea [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="e371e-111">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e371e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e371e-112">See also</span></span>

- [<span data-ttu-id="e371e-113">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="e371e-113">Tracing</span></span>](index.md)
- [<span data-ttu-id="e371e-114">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="e371e-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e371e-115">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e371e-115">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="e371e-116">Administración de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="e371e-116">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="e371e-117">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e371e-117">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span></span>
