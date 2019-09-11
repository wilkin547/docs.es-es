---
title: Contadores del rendimiento de las operaciones
ms.date: 03/30/2017
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
ms.openlocfilehash: 31b0f92ae3477bd3c1de8c348a60e5c64d7c53cc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855679"
---
# <a name="operation-performance-counters"></a><span data-ttu-id="d1fbf-102">Contadores del rendimiento de las operaciones</span><span class="sxs-lookup"><span data-stu-id="d1fbf-102">Operation Performance Counters</span></span>
<span data-ttu-id="d1fbf-103">Los contadores de rendimiento de las operaciones se encuentran bajo el objeto de rendimiento `ServiceModelOperation 4.0.0.0` al visualizarlo con el monitor de rendimiento (Perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="d1fbf-103">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="d1fbf-104">Cada operación posee una instancia individual.</span><span class="sxs-lookup"><span data-stu-id="d1fbf-104">Each operation has an individual instance.</span></span> <span data-ttu-id="d1fbf-105">Es decir, si un contrato determinado posee 10 operaciones, se asociarán 10 instancias de contador de operación a ese contrato.</span><span class="sxs-lookup"><span data-stu-id="d1fbf-105">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="d1fbf-106">Los nombres de las instancias de objeto se establecen utilizando el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="d1fbf-106">The object instances are named using the following pattern:</span></span>  
  
`(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)`
  
 <span data-ttu-id="d1fbf-107">Este contador permite medir la utilización de la llamada y el buen rendimiento de la operación.</span><span class="sxs-lookup"><span data-stu-id="d1fbf-107">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="d1fbf-108">Hay un límite en la longitud del nombre de una instancia del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d1fbf-108">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="d1fbf-109">Cuando un nombre de instancia de contador de Windows Communication Foundation (WCF) supera la longitud máxima, WCF reemplaza una parte del nombre de instancia por un valor hash.</span><span class="sxs-lookup"><span data-stu-id="d1fbf-109">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1fbf-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1fbf-110">See also</span></span>

- [<span data-ttu-id="d1fbf-111">Contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="d1fbf-111">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
