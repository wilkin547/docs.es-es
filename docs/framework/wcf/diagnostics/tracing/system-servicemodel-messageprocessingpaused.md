---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: ac1dacef94d6446aa407e4a390b9561d033af1bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087486"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="ab14e-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="ab14e-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="ab14e-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="ab14e-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="ab14e-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab14e-104">Description</span></span>  
 <span data-ttu-id="ab14e-105">Se intercambiaron los subprocesos al procesar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="ab14e-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="ab14e-106">El procesamiento de un mensaje se puede detener por las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="ab14e-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="ab14e-107">ConcurrencyMode está establecido como único o reentrante y el servicio está procesando otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="ab14e-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="ab14e-108">La transacción está habilitada y el servicio está procesando otra transacción.</span><span class="sxs-lookup"><span data-stu-id="ab14e-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="ab14e-109">El contexto de sincronización no es actual.</span><span class="sxs-lookup"><span data-stu-id="ab14e-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab14e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab14e-110">See also</span></span>

- [<span data-ttu-id="ab14e-111">Traza</span><span class="sxs-lookup"><span data-stu-id="ab14e-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="ab14e-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="ab14e-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ab14e-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ab14e-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
