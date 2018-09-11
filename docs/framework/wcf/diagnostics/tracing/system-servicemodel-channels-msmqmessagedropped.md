---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 07bef8b391a03f2c011e1d1a7c7fb4fad908e022
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44276596"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="26187-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="26187-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="26187-103">MSMQ colocó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="26187-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="26187-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="26187-104">Description</span></span>  
 <span data-ttu-id="26187-105">El seguimiento de traza indica que se quitó un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="26187-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="26187-106">Los mensajes de MSMQ pueden quitarse cuando Windows Communication Foundation (WCF) (usado con NetMsmqBinding o MsmqIntegrationBinding) no puede procesarlos.</span><span class="sxs-lookup"><span data-stu-id="26187-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="26187-107">Tales mensajes se conocen como mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="26187-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="26187-108">Se quita un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida como `Drop`.</span><span class="sxs-lookup"><span data-stu-id="26187-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="26187-109">Un mensaje quitado se quita de la cola y ya no puede recuperarse.</span><span class="sxs-lookup"><span data-stu-id="26187-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="26187-110">Consulte [de mensajes dudosos](https://go.microsoft.com/fwlink/?LinkID=99546) para obtener más detalles sobre cuándo los mensajes en dudosos y cómo configurar el servicio para controlarlos adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="26187-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26187-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="26187-111">See Also</span></span>  
 [<span data-ttu-id="26187-112">Traza</span><span class="sxs-lookup"><span data-stu-id="26187-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="26187-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="26187-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="26187-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="26187-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="26187-115">Control de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="26187-115">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)
