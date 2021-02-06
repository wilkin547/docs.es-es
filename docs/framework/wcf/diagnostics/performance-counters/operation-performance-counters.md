---
description: 'Más información acerca de: contadores de rendimiento de operaciones'
title: Contadores del rendimiento de las operaciones
ms.date: 03/30/2017
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
ms.openlocfilehash: e0a503d4d8b178d5d3f4ef240bf84c4b02a581ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655206"
---
# <a name="operation-performance-counters"></a><span data-ttu-id="16234-103">Contadores del rendimiento de las operaciones</span><span class="sxs-lookup"><span data-stu-id="16234-103">Operation Performance Counters</span></span>

<span data-ttu-id="16234-104">Los contadores de rendimiento de las operaciones se encuentran bajo el objeto de rendimiento `ServiceModelOperation 4.0.0.0` al visualizarlo con el monitor de rendimiento (Perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="16234-104">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="16234-105">Cada operación posee una instancia individual.</span><span class="sxs-lookup"><span data-stu-id="16234-105">Each operation has an individual instance.</span></span> <span data-ttu-id="16234-106">Es decir, si un contrato determinado posee 10 operaciones, se asociarán 10 instancias de contador de operación a ese contrato.</span><span class="sxs-lookup"><span data-stu-id="16234-106">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="16234-107">Los nombres de las instancias de objeto se establecen utilizando el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="16234-107">The object instances are named using the following pattern:</span></span>  
  
`(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)`
  
 <span data-ttu-id="16234-108">Este contador permite medir la utilización de la llamada y el buen rendimiento de la operación.</span><span class="sxs-lookup"><span data-stu-id="16234-108">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="16234-109">Hay un límite en la longitud del nombre de una instancia del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="16234-109">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="16234-110">Cuando un nombre de instancia de contador de Windows Communication Foundation (WCF) supera la longitud máxima, WCF reemplaza una parte del nombre de instancia por un valor hash.</span><span class="sxs-lookup"><span data-stu-id="16234-110">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16234-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="16234-111">See also</span></span>

- [<span data-ttu-id="16234-112">Contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="16234-112">Performance Counters</span></span>](index.md)
