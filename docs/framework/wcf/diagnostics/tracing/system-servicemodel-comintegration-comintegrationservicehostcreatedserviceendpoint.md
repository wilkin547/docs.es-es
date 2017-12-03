---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 474895e7fbcf1b9ed7ad7da6d28313ae4894f720
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="c98c0-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="c98c0-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="c98c0-103">No puede mover o eliminar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c98c0-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c98c0-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="c98c0-104">Description</span></span>  
 <span data-ttu-id="c98c0-105">El seguimiento indica que se produjo un error al intentar mover, eliminar o rechazar un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c98c0-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="c98c0-106">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] emplea mensajes MSMQ (cuando se utiliza con NetMsmqBinding o MsmqIntegrationBinding).Este seguimiento está relacionado con el valor elegido de la propiedad `ReceiveErrorHandling` en NetMsmqBinding o MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="c98c0-106">MSMQ messages are employed by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="c98c0-107">Este seguimiento no indica un error general del sistema.</span><span class="sxs-lookup"><span data-stu-id="c98c0-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="c98c0-108">Sin embargo, indica que la disposición del mensaje dudoso escogida produjo un error en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="c98c0-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="c98c0-109">Vea [de mensajes dudosos](http://go.microsoft.com/fwlink/?LinkID=99546) para obtener más detalles sobre cuándo los mensajes se convierten en mensajes dudosos y cómo configurar el servicio para controlarlos adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="c98c0-109">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c98c0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c98c0-110">See Also</span></span>  
 [<span data-ttu-id="c98c0-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="c98c0-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="c98c0-112">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="c98c0-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="c98c0-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c98c0-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
