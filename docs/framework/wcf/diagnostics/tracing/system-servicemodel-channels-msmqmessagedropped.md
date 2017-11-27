---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 55b489bcad85eff5adba16f6f40493c88e476505
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="5f233-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="5f233-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="5f233-103">MSMQ colocó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="5f233-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5f233-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f233-104">Description</span></span>  
 <span data-ttu-id="5f233-105">El seguimiento de traza indica que se quitó un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="5f233-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="5f233-106">Los mensajes de MSMQ pueden quitarse cuando [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (usado con NetMsmqBinding o MsmqIntegrationBinding) no puede procesarlos.</span><span class="sxs-lookup"><span data-stu-id="5f233-106">MSMQ messages can be dropped when [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="5f233-107">Tales mensajes se conocen como mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="5f233-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="5f233-108">Se quita un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida como `Drop`.</span><span class="sxs-lookup"><span data-stu-id="5f233-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="5f233-109">Un mensaje quitado se quita de la cola y ya no puede recuperarse.</span><span class="sxs-lookup"><span data-stu-id="5f233-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="5f233-110">Vea [de mensajes dudosos](http://go.microsoft.com/fwlink/?LinkID=99546) para obtener más detalles sobre cuándo los mensajes se convierten en mensajes dudosos y cómo configurar el servicio para controlarlos adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="5f233-110">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f233-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f233-111">See Also</span></span>  
 [<span data-ttu-id="5f233-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="5f233-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="5f233-113">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="5f233-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="5f233-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5f233-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="5f233-115">Control de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="5f233-115">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkID=99546)
