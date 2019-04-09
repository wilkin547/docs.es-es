---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: ac1dacef94d6446aa407e4a390b9561d033af1bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087486"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="b3085-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="b3085-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="b3085-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="b3085-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="b3085-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3085-104">Description</span></span>  
 <span data-ttu-id="b3085-105">Se intercambiaron los subprocesos al procesar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="b3085-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="b3085-106">El procesamiento de un mensaje se puede detener por las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="b3085-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="b3085-107">ConcurrencyMode está establecido como único o reentrante y el servicio está procesando otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="b3085-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="b3085-108">La transacción está habilitada y el servicio está procesando otra transacción.</span><span class="sxs-lookup"><span data-stu-id="b3085-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="b3085-109">El contexto de sincronización no es actual.</span><span class="sxs-lookup"><span data-stu-id="b3085-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3085-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3085-110">See also</span></span>

- [<span data-ttu-id="b3085-111">Traza</span><span class="sxs-lookup"><span data-stu-id="b3085-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="b3085-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="b3085-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b3085-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b3085-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
