---
title: System.ServiceModel.MessageProcessingPaused
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6f767165486ac2dc6ce4ee5b3e0825eceef0c249
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="19c58-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="19c58-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="19c58-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="19c58-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="19c58-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="19c58-104">Description</span></span>  
 <span data-ttu-id="19c58-105">Se intercambiaron los subprocesos al procesar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="19c58-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="19c58-106">El procesamiento de un mensaje se puede detener por las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="19c58-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="19c58-107">ConcurrencyMode está establecido como único o reentrante y el servicio está procesando otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="19c58-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="19c58-108">La transacción está habilitada y el servicio está procesando otra transacción.</span><span class="sxs-lookup"><span data-stu-id="19c58-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="19c58-109">El contexto de sincronización no es actual.</span><span class="sxs-lookup"><span data-stu-id="19c58-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c58-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="19c58-110">See Also</span></span>  
 [<span data-ttu-id="19c58-111">Traza</span><span class="sxs-lookup"><span data-stu-id="19c58-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="19c58-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="19c58-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="19c58-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="19c58-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
