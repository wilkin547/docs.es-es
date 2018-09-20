---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 0addf987eac62c750a3c418e1b1c431d3f9bc1b0
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46484953"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="e4e82-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="e4e82-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="e4e82-103">MSMQ rechazó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e4e82-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e4e82-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4e82-104">Description</span></span>  
 <span data-ttu-id="e4e82-105">Este seguimiento indica que se rechazó un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e4e82-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="e4e82-106">Cuando Windows Communication Foundation (WCF) (usado con NetMsmqBinding o MsmqIntegrationBinding) no puede procesarlos, se pueden rechazar mensajes de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e4e82-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="e4e82-107">Tales mensajes se conocen como mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="e4e82-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="e4e82-108">Se rechaza un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida en `Reject`.</span><span class="sxs-lookup"><span data-stu-id="e4e82-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="e4e82-109">Un mensaje rechazado se entrega al remitente [cola](https://go.microsoft.com/fwlink/?LinkID=99544).</span><span class="sxs-lookup"><span data-stu-id="e4e82-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkID=99544).</span></span>  
  
 <span data-ttu-id="e4e82-110">Consulte [de mensajes dudosos](https://go.microsoft.com/fwlink/?LinkID=99546) para obtener más detalles sobre cuándo los mensajes en dudosos y cómo configurar el servicio para controlarlos adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="e4e82-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
 <span data-ttu-id="e4e82-111">Consulte [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) para obtener más detalles sobre lo que significa un mensaje rechazado en MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e4e82-111">See [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e82-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4e82-112">See Also</span></span>  
 [<span data-ttu-id="e4e82-113">Traza</span><span class="sxs-lookup"><span data-stu-id="e4e82-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="e4e82-114">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="e4e82-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="e4e82-115">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e4e82-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="e4e82-116">Control de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="e4e82-116">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)  
 [<span data-ttu-id="e4e82-117">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="e4e82-117">MQMarkMessageRejected</span></span>](https://go.microsoft.com/fwlink/?LinkID=99548)
