---
description: 'Más información sobre: System. ServiceModel. Channels. MsmqMessageDropped'
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 41b9c6d5399f0f6b458404ee4b64624e5863c777
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780965"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="806e2-103">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="806e2-103">System.ServiceModel.Channels.MsmqMessageDropped</span></span>

<span data-ttu-id="806e2-104">MSMQ colocó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="806e2-104">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="806e2-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="806e2-105">Description</span></span>  

 <span data-ttu-id="806e2-106">El seguimiento de traza indica que se quitó un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="806e2-106">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="806e2-107">Los mensajes de MSMQ se pueden quitar cuando Windows Communication Foundation (WCF) (que se usa con NetMsmqBinding o MsmqIntegrationBinding) no puede procesarlos.</span><span class="sxs-lookup"><span data-stu-id="806e2-107">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="806e2-108">Tales mensajes se conocen como mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="806e2-108">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="806e2-109">Se quita un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida como `Drop`.</span><span class="sxs-lookup"><span data-stu-id="806e2-109">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="806e2-110">Un mensaje quitado se quita de la cola y ya no puede recuperarse.</span><span class="sxs-lookup"><span data-stu-id="806e2-110">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="806e2-111">Para obtener más información sobre cuándo los mensajes son dudosos y cómo configurar el servicio para controlarlos adecuadamente, vea [control de mensajes dudosos](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="806e2-111">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="806e2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="806e2-112">See also</span></span>

- [<span data-ttu-id="806e2-113">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="806e2-113">Tracing</span></span>](index.md)
- [<span data-ttu-id="806e2-114">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="806e2-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="806e2-115">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="806e2-115">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="806e2-116">Administración de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="806e2-116">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
