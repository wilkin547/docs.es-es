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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1176af676673e19eb2d8cd54cc4d2d254c7ba324
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="69f00-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="69f00-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="69f00-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="69f00-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="69f00-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="69f00-104">Description</span></span>  
 <span data-ttu-id="69f00-105">Se intercambiaron los subprocesos al procesar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="69f00-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="69f00-106">El procesamiento de un mensaje se puede detener por las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="69f00-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="69f00-107">ConcurrencyMode está establecido como único o reentrante y el servicio está procesando otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="69f00-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="69f00-108">La transacción está habilitada y el servicio está procesando otra transacción.</span><span class="sxs-lookup"><span data-stu-id="69f00-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="69f00-109">El contexto de sincronización no es actual.</span><span class="sxs-lookup"><span data-stu-id="69f00-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69f00-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="69f00-110">See Also</span></span>  
 [<span data-ttu-id="69f00-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="69f00-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="69f00-112">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="69f00-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="69f00-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="69f00-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
