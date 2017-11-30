---
title: Contadores del rendimiento de las operaciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 83460e1c4db17938466051269dbeba3f19e0b40a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="operation-performance-counters"></a><span data-ttu-id="83521-102">Contadores del rendimiento de las operaciones</span><span class="sxs-lookup"><span data-stu-id="83521-102">Operation Performance Counters</span></span>
<span data-ttu-id="83521-103">Los contadores de rendimiento de las operaciones se encuentran bajo el objeto de rendimiento `ServiceModelOperation 4.0.0.0` al visualizarlo con el monitor de rendimiento (Perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="83521-103">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="83521-104">Cada operación posee una instancia individual.</span><span class="sxs-lookup"><span data-stu-id="83521-104">Each operation has an individual instance.</span></span> <span data-ttu-id="83521-105">Es decir, si un contrato determinado posee 10 operaciones, se asociarán 10 instancias de contador de operación a ese contrato.</span><span class="sxs-lookup"><span data-stu-id="83521-105">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="83521-106">Los nombres de las instancias de objeto se establecen utilizando el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="83521-106">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="83521-107">Este contador permite medir la utilización de la llamada y el buen rendimiento de la operación.</span><span class="sxs-lookup"><span data-stu-id="83521-107">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="83521-108">Hay un límite en la longitud del nombre de una instancia del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="83521-108">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="83521-109">Cuando un nombre de instancia de contador [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] supera la longitud máxima, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] reemplaza una parte del nombre de instancia con un valor hash.</span><span class="sxs-lookup"><span data-stu-id="83521-109">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83521-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="83521-110">See Also</span></span>  
 [<span data-ttu-id="83521-111">Contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="83521-111">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
