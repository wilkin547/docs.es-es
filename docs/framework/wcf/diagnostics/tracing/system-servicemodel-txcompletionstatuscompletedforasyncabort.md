---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: a243acc3d8a17e4a53b3d05e3420f481f7b6dc6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486036"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="28ec7-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="28ec7-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="28ec7-103">La transacción especificada para la operación definida se completó debido a la anulación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="28ec7-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="28ec7-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="28ec7-104">Description</span></span>  
 <span data-ttu-id="28ec7-105">Se anuló la transacción actual debido a que otro participante eligió la interrupción, se produjo tiempo de espera u otro error dentro del participante de una transacción.</span><span class="sxs-lookup"><span data-stu-id="28ec7-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="28ec7-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="28ec7-106">Troubleshooting</span></span>  
 <span data-ttu-id="28ec7-107">Si no se esperaba la anulación, compruebe todos los registros de sistema para determinar la verdadera razón de la anulación.</span><span class="sxs-lookup"><span data-stu-id="28ec7-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ec7-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="28ec7-108">See Also</span></span>  
 [<span data-ttu-id="28ec7-109">Traza</span><span class="sxs-lookup"><span data-stu-id="28ec7-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="28ec7-110">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="28ec7-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="28ec7-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="28ec7-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
