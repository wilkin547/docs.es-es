---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 7dcdb9fdd6a283f692897cbbb49cd1f2d1dd661e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586788"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="55f64-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="55f64-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="55f64-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="55f64-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="55f64-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="55f64-104">Description</span></span>  
 <span data-ttu-id="55f64-105">Se intercambiaron los subprocesos al procesar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="55f64-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="55f64-106">El procesamiento de un mensaje se puede detener por las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="55f64-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="55f64-107">ConcurrencyMode está establecido como único o reentrante y el servicio está procesando otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="55f64-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="55f64-108">La transacción está habilitada y el servicio está procesando otra transacción.</span><span class="sxs-lookup"><span data-stu-id="55f64-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="55f64-109">El contexto de sincronización no es actual.</span><span class="sxs-lookup"><span data-stu-id="55f64-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55f64-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="55f64-110">See also</span></span>

- [<span data-ttu-id="55f64-111">Traza</span><span class="sxs-lookup"><span data-stu-id="55f64-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="55f64-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="55f64-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="55f64-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="55f64-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
