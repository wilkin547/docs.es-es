---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: e4c8040d2350e3824b5d68dc6f32376007792a7f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235121"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="24c7c-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="24c7c-102">System.ServiceModel.MessageProcessingPaused</span></span>

<span data-ttu-id="24c7c-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="24c7c-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="24c7c-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="24c7c-104">Description</span></span>  

 <span data-ttu-id="24c7c-105">Se intercambiaron los subprocesos al procesar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="24c7c-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="24c7c-106">El procesamiento de un mensaje se puede detener por las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="24c7c-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="24c7c-107">ConcurrencyMode está establecido como único o reentrante y el servicio está procesando otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="24c7c-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="24c7c-108">La transacción está habilitada y el servicio está procesando otra transacción.</span><span class="sxs-lookup"><span data-stu-id="24c7c-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="24c7c-109">El contexto de sincronización no es actual.</span><span class="sxs-lookup"><span data-stu-id="24c7c-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c7c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="24c7c-110">See also</span></span>

- [<span data-ttu-id="24c7c-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="24c7c-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="24c7c-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="24c7c-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="24c7c-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="24c7c-113">Administration and Diagnostics</span></span>](../index.md)
