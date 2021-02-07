---
description: 'Más información sobre: System. ServiceModel. MessageProcessingPaused'
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 77e4742bc5617904136b2ddd9cb90fe886d38b10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716187"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="06c8e-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="06c8e-103">System.ServiceModel.MessageProcessingPaused</span></span>

<span data-ttu-id="06c8e-104">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="06c8e-104">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="06c8e-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="06c8e-105">Description</span></span>  

 <span data-ttu-id="06c8e-106">Se intercambiaron los subprocesos al procesar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="06c8e-106">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="06c8e-107">El procesamiento de un mensaje se puede detener por las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="06c8e-107">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="06c8e-108">ConcurrencyMode está establecido como único o reentrante y el servicio está procesando otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="06c8e-108">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="06c8e-109">La transacción está habilitada y el servicio está procesando otra transacción.</span><span class="sxs-lookup"><span data-stu-id="06c8e-109">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="06c8e-110">El contexto de sincronización no es actual.</span><span class="sxs-lookup"><span data-stu-id="06c8e-110">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06c8e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="06c8e-111">See also</span></span>

- [<span data-ttu-id="06c8e-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="06c8e-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="06c8e-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="06c8e-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="06c8e-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="06c8e-114">Administration and Diagnostics</span></span>](../index.md)
