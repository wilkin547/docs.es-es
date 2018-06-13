---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 2bd64263a2374c10a3514cbed75f9224542051dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33478951"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="4bc77-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="4bc77-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="4bc77-103">MSMQ rechazó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="4bc77-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4bc77-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bc77-104">Description</span></span>  
 <span data-ttu-id="4bc77-105">Este seguimiento indica que se rechazó un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="4bc77-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="4bc77-106">Mensajes de MSMQ pueden rechazarse cuando Windows Communication Foundation (WCF) (usado con NetMsmqBinding o MsmqIntegrationBinding) no puede procesarlos.</span><span class="sxs-lookup"><span data-stu-id="4bc77-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="4bc77-107">Tales mensajes se conocen como mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="4bc77-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="4bc77-108">Se rechaza un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida en `Reject`.</span><span class="sxs-lookup"><span data-stu-id="4bc77-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="4bc77-109">Se entrega un mensaje rechazado hacia el remitente [cola de mensajes](http://go.microsoft.com/fwlink/?LinkID=99544).</span><span class="sxs-lookup"><span data-stu-id="4bc77-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](http://go.microsoft.com/fwlink/?LinkID=99544).</span></span>  
  
 <span data-ttu-id="4bc77-110">Vea [de mensajes dudosos](http://go.microsoft.com/fwlink/?LinkID=99546) para obtener más detalles sobre cuándo los mensajes se convierten en mensajes dudosos y cómo configurar el servicio para controlarlos adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="4bc77-110">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
 <span data-ttu-id="4bc77-111">Vea [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) para obtener más detalles sobre lo que significa un mensaje rechazado en MSMQ.</span><span class="sxs-lookup"><span data-stu-id="4bc77-111">See [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bc77-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bc77-112">See Also</span></span>  
 [<span data-ttu-id="4bc77-113">Traza</span><span class="sxs-lookup"><span data-stu-id="4bc77-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="4bc77-114">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="4bc77-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="4bc77-115">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="4bc77-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="4bc77-116">Control de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="4bc77-116">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkID=99546)  
 [<span data-ttu-id="4bc77-117">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="4bc77-117">MQMarkMessageRejected</span></span>](http://go.microsoft.com/fwlink/?LinkID=99548)
