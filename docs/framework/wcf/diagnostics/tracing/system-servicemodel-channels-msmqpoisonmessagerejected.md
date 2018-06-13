---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 7dc1e4120caae7c4a592067f5e77ed4f56e82e6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33478171"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="18cfd-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="18cfd-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="18cfd-103">Mensaje dudoso rechazado.</span><span class="sxs-lookup"><span data-stu-id="18cfd-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="18cfd-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="18cfd-104">Description</span></span>  
 <span data-ttu-id="18cfd-105">El seguimiento de traza indica que se encontró un mensaje dudoso y fue posteriormente rechazado.</span><span class="sxs-lookup"><span data-stu-id="18cfd-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="18cfd-106">Esto sucede cuando la propiedad `ReceiveErrorHandling` en NetMsmqBinding o MsmqIntegrationBinding está establecida en `Reject`.</span><span class="sxs-lookup"><span data-stu-id="18cfd-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="18cfd-107">Se entrega un mensaje rechazado hacia el remitente [cola de mensajes](http://go.microsoft.com/fwlink/?LinkId=99544).</span><span class="sxs-lookup"><span data-stu-id="18cfd-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](http://go.microsoft.com/fwlink/?LinkId=99544).</span></span>  
  
 <span data-ttu-id="18cfd-108">Vea [de mensajes dudosos](http://go.microsoft.com/fwlink/?LinkId=99546) para obtener más detalles sobre cuándo los mensajes se convierten en mensajes dudosos y cómo configurar el servicio para controlarlos adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="18cfd-108">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkId=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span> <span data-ttu-id="18cfd-109">Vea [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) para obtener más detalles sobre lo que significa un mensaje rechazado en MSMQ.</span><span class="sxs-lookup"><span data-stu-id="18cfd-109">See [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18cfd-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="18cfd-110">See Also</span></span>  
 [<span data-ttu-id="18cfd-111">Traza</span><span class="sxs-lookup"><span data-stu-id="18cfd-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="18cfd-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="18cfd-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="18cfd-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="18cfd-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="18cfd-114">Control de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="18cfd-114">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkId=99546)  
 [<span data-ttu-id="18cfd-115">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="18cfd-115">MQMarkMessageRejected</span></span>](http://go.microsoft.com/fwlink/?LinkId=99548)
