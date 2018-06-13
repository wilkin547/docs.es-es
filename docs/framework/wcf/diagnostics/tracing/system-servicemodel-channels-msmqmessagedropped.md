---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: ad05a2b8552cc09d45e950e2c3336d86be918963
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33479136"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="ed289-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="ed289-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="ed289-103">MSMQ colocó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ed289-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ed289-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed289-104">Description</span></span>  
 <span data-ttu-id="ed289-105">El seguimiento de traza indica que se quitó un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ed289-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="ed289-106">Mensajes MSMQ pueden quitarse cuando Windows Communication Foundation (WCF) (usado con NetMsmqBinding o MsmqIntegrationBinding) no puede procesarlos.</span><span class="sxs-lookup"><span data-stu-id="ed289-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="ed289-107">Tales mensajes se conocen como mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="ed289-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="ed289-108">Se quita un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida como `Drop`.</span><span class="sxs-lookup"><span data-stu-id="ed289-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="ed289-109">Un mensaje quitado se quita de la cola y ya no puede recuperarse.</span><span class="sxs-lookup"><span data-stu-id="ed289-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="ed289-110">Vea [de mensajes dudosos](http://go.microsoft.com/fwlink/?LinkID=99546) para obtener más detalles sobre cuándo los mensajes se convierten en mensajes dudosos y cómo configurar el servicio para controlarlos adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="ed289-110">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed289-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed289-111">See Also</span></span>  
 [<span data-ttu-id="ed289-112">Traza</span><span class="sxs-lookup"><span data-stu-id="ed289-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="ed289-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="ed289-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="ed289-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ed289-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="ed289-115">Control de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="ed289-115">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkID=99546)
