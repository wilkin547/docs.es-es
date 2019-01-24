---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: c8e476ab90fda9214831fbd5beaba518f3e3bd20
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491433"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="ec69b-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="ec69b-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="ec69b-103">Mensaje dudoso rechazado.</span><span class="sxs-lookup"><span data-stu-id="ec69b-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ec69b-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec69b-104">Description</span></span>  
 <span data-ttu-id="ec69b-105">El seguimiento de traza indica que se encontró un mensaje dudoso y fue posteriormente rechazado.</span><span class="sxs-lookup"><span data-stu-id="ec69b-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="ec69b-106">Esto sucede cuando la propiedad `ReceiveErrorHandling` en NetMsmqBinding o MsmqIntegrationBinding está establecida en `Reject`.</span><span class="sxs-lookup"><span data-stu-id="ec69b-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="ec69b-107">Un mensaje rechazado se entrega al remitente [cola](https://go.microsoft.com/fwlink/?LinkId=99544).</span><span class="sxs-lookup"><span data-stu-id="ec69b-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkId=99544).</span></span>  
  
 <span data-ttu-id="ec69b-108">Consulte [de mensajes dudosos](https://go.microsoft.com/fwlink/?LinkId=99546) para obtener más detalles sobre cuándo los mensajes en dudosos y cómo configurar el servicio para controlarlos adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="ec69b-108">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkId=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span> <span data-ttu-id="ec69b-109">Consulte [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548) para obtener más detalles sobre lo que significa un mensaje rechazado en MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ec69b-109">See [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec69b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec69b-110">See also</span></span>
- [<span data-ttu-id="ec69b-111">Traza</span><span class="sxs-lookup"><span data-stu-id="ec69b-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="ec69b-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="ec69b-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ec69b-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ec69b-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="ec69b-114">Control de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="ec69b-114">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkId=99546)
- [<span data-ttu-id="ec69b-115">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="ec69b-115">MQMarkMessageRejected</span></span>](https://go.microsoft.com/fwlink/?LinkId=99548)
