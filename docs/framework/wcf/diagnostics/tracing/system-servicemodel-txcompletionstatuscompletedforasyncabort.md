---
description: 'Más información sobre: System. ServiceModel. TxCompletionStatusCompletedForAsyncAbort'
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: 892a867607d1c6d34c06a59947cc336db067fb19
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735691"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="86816-103">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="86816-103">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>

<span data-ttu-id="86816-104">La transacción especificada para la operación definida se completó debido a la anulación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="86816-104">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="86816-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="86816-105">Description</span></span>  

 <span data-ttu-id="86816-106">Se anuló la transacción actual debido a que otro participante eligió la interrupción, se produjo tiempo de espera u otro error dentro del participante de una transacción.</span><span class="sxs-lookup"><span data-stu-id="86816-106">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="86816-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="86816-107">Troubleshooting</span></span>  

 <span data-ttu-id="86816-108">Si no se esperaba la anulación, compruebe todos los registros de sistema para determinar la verdadera razón de la anulación.</span><span class="sxs-lookup"><span data-stu-id="86816-108">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86816-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="86816-109">See also</span></span>

- [<span data-ttu-id="86816-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="86816-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="86816-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="86816-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="86816-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="86816-112">Administration and Diagnostics</span></span>](../index.md)
