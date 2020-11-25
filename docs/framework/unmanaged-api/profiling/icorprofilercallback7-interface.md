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
ms.openlocfilehash: e9c7186b3217c29805327e6c1d6b10f580c3a9e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725461"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="071d0-102">Interfaz ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="071d0-102">ICorProfilerCallback7 Interface</span></span>

<span data-ttu-id="071d0-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="071d0-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="071d0-104">Una subclase de [ICorProfilerCallback6](icorprofilercallback6-interface.md) que proporciona un método de devolución de llamada que Common Language Runtime utiliza para notificar al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="071d0-104">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="071d0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="071d0-105">Methods</span></span>  
  
|<span data-ttu-id="071d0-106">Método</span><span class="sxs-lookup"><span data-stu-id="071d0-106">Method</span></span>|<span data-ttu-id="071d0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="071d0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="071d0-108">Método ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="071d0-108">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="071d0-109">Notifica al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="071d0-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="071d0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="071d0-110">Requirements</span></span>  

 <span data-ttu-id="071d0-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="071d0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="071d0-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="071d0-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="071d0-113">**.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="071d0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="071d0-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="071d0-114">See also</span></span>

- [<span data-ttu-id="071d0-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="071d0-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
