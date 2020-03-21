---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 6b0e6e3ebcf5d414e9dbbcecd09ba2e8bb3ddd3a
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674809"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="2cede-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="2cede-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="2cede-103">Mensaje dudoso rechazado.</span><span class="sxs-lookup"><span data-stu-id="2cede-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2cede-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="2cede-104">Description</span></span>  

 <span data-ttu-id="2cede-105">El seguimiento de traza indica que se encontró un mensaje dudoso y fue posteriormente rechazado.</span><span class="sxs-lookup"><span data-stu-id="2cede-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="2cede-106">Esto sucede cuando la propiedad `ReceiveErrorHandling` en NetMsmqBinding o MsmqIntegrationBinding está establecida en `Reject`.</span><span class="sxs-lookup"><span data-stu-id="2cede-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="2cede-107">Un mensaje rechazado se devuelve a la [cola de mensajes no](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)enviados del remitente.</span><span class="sxs-lookup"><span data-stu-id="2cede-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="2cede-108">Para obtener más información sobre cuándo los mensajes se vuelven dudosos y cómo configurar el servicio para que los controle adecuadamente, vea [Manejo de mensajes envenenados](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="2cede-108">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="2cede-109">Para obtener más información sobre lo que significa un mensaje rechazado en MSMQ, vea [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span><span class="sxs-lookup"><span data-stu-id="2cede-109">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cede-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2cede-110">See also</span></span>

- [<span data-ttu-id="2cede-111">Rastreo</span><span class="sxs-lookup"><span data-stu-id="2cede-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="2cede-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="2cede-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2cede-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2cede-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="2cede-114">Administración de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="2cede-114">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="2cede-115">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="2cede-115">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
