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
ms.openlocfilehash: 2a99e8b3158da9d473d50bc7792ce9e2aa19bb27
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="368cd-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="368cd-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="368cd-103">La transacción especificada para la operación definida se completó debido a la anulación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="368cd-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="368cd-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="368cd-104">Description</span></span>  
 <span data-ttu-id="368cd-105">Se anuló la transacción actual debido a que otro participante eligió la interrupción, se produjo tiempo de espera u otro error dentro del participante de una transacción.</span><span class="sxs-lookup"><span data-stu-id="368cd-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="368cd-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="368cd-106">Troubleshooting</span></span>  
 <span data-ttu-id="368cd-107">Si no se esperaba la anulación, compruebe todos los registros de sistema para determinar la verdadera razón de la anulación.</span><span class="sxs-lookup"><span data-stu-id="368cd-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="368cd-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="368cd-108">See Also</span></span>  
 [<span data-ttu-id="368cd-109">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="368cd-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="368cd-110">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="368cd-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="368cd-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="368cd-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
