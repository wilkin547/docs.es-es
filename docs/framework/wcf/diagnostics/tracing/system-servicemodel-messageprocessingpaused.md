---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 85bec8255e0d20d6e76ea354e5b8c42b83d7d8e6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598156"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="e102e-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="e102e-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="e102e-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="e102e-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="e102e-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="e102e-104">Description</span></span>  
 <span data-ttu-id="e102e-105">Se intercambiaron los subprocesos al procesar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="e102e-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="e102e-106">El procesamiento de un mensaje se puede detener por las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="e102e-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="e102e-107">ConcurrencyMode está establecido como único o reentrante y el servicio está procesando otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="e102e-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="e102e-108">La transacción está habilitada y el servicio está procesando otra transacción.</span><span class="sxs-lookup"><span data-stu-id="e102e-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="e102e-109">El contexto de sincronización no es actual.</span><span class="sxs-lookup"><span data-stu-id="e102e-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e102e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e102e-110">See also</span></span>

- [<span data-ttu-id="e102e-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="e102e-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="e102e-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="e102e-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e102e-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e102e-113">Administration and Diagnostics</span></span>](../index.md)
