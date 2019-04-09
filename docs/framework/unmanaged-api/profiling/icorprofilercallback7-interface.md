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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178638"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="f41a0-102">Interfaz ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="f41a0-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="f41a0-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="f41a0-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="f41a0-104">Una subclase de [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) que proporciona un método de devolución de llamada que Common Language Runtime utiliza para notificar al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="f41a0-104">A subclass of [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f41a0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f41a0-105">Methods</span></span>  
  
|<span data-ttu-id="f41a0-106">Método</span><span class="sxs-lookup"><span data-stu-id="f41a0-106">Method</span></span>|<span data-ttu-id="f41a0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f41a0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f41a0-108">Método ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="f41a0-108">ModuleInMemorySymbolsUpdated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="f41a0-109">Notifica al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="f41a0-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f41a0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f41a0-110">Requirements</span></span>  
 <span data-ttu-id="f41a0-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f41a0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f41a0-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f41a0-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="f41a0-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f41a0-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f41a0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f41a0-114">See also</span></span>

- [<span data-ttu-id="f41a0-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f41a0-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
