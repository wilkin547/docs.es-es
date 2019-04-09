---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 3fa5ec62c5e8ac83f3f81fb406499b7e596b3dac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161345"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="a8f9a-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="a8f9a-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="a8f9a-103">MSMQ colocó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a8f9a-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a8f9a-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8f9a-104">Description</span></span>  
 <span data-ttu-id="a8f9a-105">El seguimiento de traza indica que se quitó un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="a8f9a-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="a8f9a-106">Los mensajes de MSMQ pueden quitarse cuando Windows Communication Foundation (WCF) (usado con NetMsmqBinding o MsmqIntegrationBinding) no puede procesarlos.</span><span class="sxs-lookup"><span data-stu-id="a8f9a-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="a8f9a-107">Tales mensajes se conocen como mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="a8f9a-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="a8f9a-108">Se quita un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida como `Drop`.</span><span class="sxs-lookup"><span data-stu-id="a8f9a-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="a8f9a-109">Un mensaje quitado se quita de la cola y ya no puede recuperarse.</span><span class="sxs-lookup"><span data-stu-id="a8f9a-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="a8f9a-110">Consulte [de mensajes dudosos](https://go.microsoft.com/fwlink/?LinkID=99546) para obtener más detalles sobre cuándo los mensajes en dudosos y cómo configurar el servicio para controlarlos adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="a8f9a-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f9a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8f9a-111">See also</span></span>

- [<span data-ttu-id="a8f9a-112">Traza</span><span class="sxs-lookup"><span data-stu-id="a8f9a-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="a8f9a-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="a8f9a-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="a8f9a-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="a8f9a-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="a8f9a-115">Administración de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="a8f9a-115">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)
