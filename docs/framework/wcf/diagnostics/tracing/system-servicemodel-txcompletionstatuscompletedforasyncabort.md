---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf6c70bdcfc402322dd1f20bbff2be74c111798a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="2b3a9-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="2b3a9-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="2b3a9-103">La transacción especificada para la operación definida se completó debido a la anulación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="2b3a9-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2b3a9-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b3a9-104">Description</span></span>  
 <span data-ttu-id="2b3a9-105">Se anuló la transacción actual debido a que otro participante eligió la interrupción, se produjo tiempo de espera u otro error dentro del participante de una transacción.</span><span class="sxs-lookup"><span data-stu-id="2b3a9-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2b3a9-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="2b3a9-106">Troubleshooting</span></span>  
 <span data-ttu-id="2b3a9-107">Si no se esperaba la anulación, compruebe todos los registros de sistema para determinar la verdadera razón de la anulación.</span><span class="sxs-lookup"><span data-stu-id="2b3a9-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b3a9-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b3a9-108">See Also</span></span>  
 [<span data-ttu-id="2b3a9-109">Traza</span><span class="sxs-lookup"><span data-stu-id="2b3a9-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="2b3a9-110">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="2b3a9-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="2b3a9-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2b3a9-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
