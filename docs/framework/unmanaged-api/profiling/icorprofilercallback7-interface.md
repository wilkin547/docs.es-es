---
title: Interfaz ICorProfilerCallback7
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type: COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 09de947b3f965f25942bd3e3081d91d3028532f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="3f970-102">Interfaz ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="3f970-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="3f970-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="3f970-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="3f970-104">Una subclase de [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) que proporciona un método de devolución de llamada que Common Language Runtime utiliza para notificar al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="3f970-104">A subclass of [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3f970-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3f970-105">Methods</span></span>  
  
|<span data-ttu-id="3f970-106">Método</span><span class="sxs-lookup"><span data-stu-id="3f970-106">Method</span></span>|<span data-ttu-id="3f970-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f970-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3f970-108">ModuleInMemorySymbolsUpdated (método)</span><span class="sxs-lookup"><span data-stu-id="3f970-108">ModuleInMemorySymbolsUpdated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="3f970-109">Notifica al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="3f970-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3f970-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f970-110">Requirements</span></span>  
 <span data-ttu-id="3f970-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f970-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f970-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3f970-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3f970-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f970-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f970-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f970-114">See Also</span></span>  
 [<span data-ttu-id="3f970-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="3f970-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
