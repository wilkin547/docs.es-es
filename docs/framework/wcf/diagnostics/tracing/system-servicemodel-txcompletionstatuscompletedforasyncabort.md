---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: f84cc9336d6cce7d8c477a1feb6caf45b0662177
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188479"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="4d22b-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="4d22b-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="4d22b-103">La transacción especificada para la operación definida se completó debido a la anulación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="4d22b-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4d22b-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d22b-104">Description</span></span>  
 <span data-ttu-id="4d22b-105">Se anuló la transacción actual debido a que otro participante eligió la interrupción, se produjo tiempo de espera u otro error dentro del participante de una transacción.</span><span class="sxs-lookup"><span data-stu-id="4d22b-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="4d22b-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="4d22b-106">Troubleshooting</span></span>  
 <span data-ttu-id="4d22b-107">Si no se esperaba la anulación, compruebe todos los registros de sistema para determinar la verdadera razón de la anulación.</span><span class="sxs-lookup"><span data-stu-id="4d22b-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d22b-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d22b-108">See also</span></span>

- [<span data-ttu-id="4d22b-109">Traza</span><span class="sxs-lookup"><span data-stu-id="4d22b-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="4d22b-110">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="4d22b-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="4d22b-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="4d22b-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
