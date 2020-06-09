---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 4b016f53a75d9527a5cd1bbadacacd650b7f35b0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601925"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="dab7e-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="dab7e-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="dab7e-103">MSMQ colocó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="dab7e-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="dab7e-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="dab7e-104">Description</span></span>  
 <span data-ttu-id="dab7e-105">El seguimiento de traza indica que se quitó un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="dab7e-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="dab7e-106">Los mensajes de MSMQ se pueden quitar cuando Windows Communication Foundation (WCF) (que se usa con NetMsmqBinding o MsmqIntegrationBinding) no puede procesarlos.</span><span class="sxs-lookup"><span data-stu-id="dab7e-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="dab7e-107">Tales mensajes se conocen como mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="dab7e-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="dab7e-108">Se quita un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida como `Drop`.</span><span class="sxs-lookup"><span data-stu-id="dab7e-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="dab7e-109">Un mensaje quitado se quita de la cola y ya no puede recuperarse.</span><span class="sxs-lookup"><span data-stu-id="dab7e-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="dab7e-110">Para obtener más información sobre cuándo los mensajes son dudosos y cómo configurar el servicio para controlarlos adecuadamente, vea [control de mensajes dudosos](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="dab7e-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab7e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="dab7e-111">See also</span></span>

- [<span data-ttu-id="dab7e-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="dab7e-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="dab7e-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="dab7e-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="dab7e-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="dab7e-114">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="dab7e-115">Administración de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="dab7e-115">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
