---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: e80fecf508158dcb53f08b75c8f9486c13e403a4
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674800"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="e0338-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="e0338-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="e0338-103">MSMQ colocó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e0338-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e0338-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0338-104">Description</span></span>  
 <span data-ttu-id="e0338-105">El seguimiento de traza indica que se quitó un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e0338-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="e0338-106">Los mensajes MSMQ se pueden quitar cuando Windows Communication Foundation (WCF) (utilizado con NetMsmqBinding o MsmqIntegrationBinding) no puede procesarlos.</span><span class="sxs-lookup"><span data-stu-id="e0338-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="e0338-107">Tales mensajes se conocen como mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="e0338-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="e0338-108">Se quita un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida como `Drop`.</span><span class="sxs-lookup"><span data-stu-id="e0338-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="e0338-109">Un mensaje quitado se quita de la cola y ya no puede recuperarse.</span><span class="sxs-lookup"><span data-stu-id="e0338-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="e0338-110">Para obtener más información sobre cuándo los mensajes se vuelven dudosos y cómo configurar el servicio para que los controle adecuadamente, vea [Manejo de mensajes envenenados](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="e0338-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0338-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0338-111">See also</span></span>

- [<span data-ttu-id="e0338-112">Rastreo</span><span class="sxs-lookup"><span data-stu-id="e0338-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="e0338-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="e0338-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e0338-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e0338-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="e0338-115">Administración de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="e0338-115">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
