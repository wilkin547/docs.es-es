---
title: Interfaz ICorProfilerCallback7
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81477010b22edee71098edfc1b8557db08b6038f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049705"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="7f63e-102">Interfaz ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="7f63e-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="7f63e-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="7f63e-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="7f63e-104">Una subclase de [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) que proporciona un método de devolución de llamada que Common Language Runtime utiliza para notificar al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="7f63e-104">A subclass of [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7f63e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7f63e-105">Methods</span></span>  
  
|<span data-ttu-id="7f63e-106">Método</span><span class="sxs-lookup"><span data-stu-id="7f63e-106">Method</span></span>|<span data-ttu-id="7f63e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f63e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7f63e-108">ModuleInMemorySymbolsUpdated (método)</span><span class="sxs-lookup"><span data-stu-id="7f63e-108">ModuleInMemorySymbolsUpdated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="7f63e-109">Notifica al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="7f63e-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f63e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f63e-110">Requirements</span></span>  
 <span data-ttu-id="7f63e-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f63e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f63e-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7f63e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7f63e-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f63e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f63e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f63e-114">See also</span></span>

- [<span data-ttu-id="7f63e-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="7f63e-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
