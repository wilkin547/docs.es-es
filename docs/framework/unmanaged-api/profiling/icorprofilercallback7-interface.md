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
ms.openlocfilehash: e61f6a104b8b9613db32ed6912395fd07c18dcff
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864822"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="bce2a-102">Interfaz ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="bce2a-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="bce2a-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="bce2a-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="bce2a-104">Una subclase de [ICorProfilerCallback6](icorprofilercallback6-interface.md) que proporciona un método de devolución de llamada que Common Language Runtime utiliza para notificar al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="bce2a-104">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bce2a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="bce2a-105">Methods</span></span>  
  
|<span data-ttu-id="bce2a-106">Método</span><span class="sxs-lookup"><span data-stu-id="bce2a-106">Method</span></span>|<span data-ttu-id="bce2a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bce2a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bce2a-108">ModuleInMemorySymbolsUpdated (método)</span><span class="sxs-lookup"><span data-stu-id="bce2a-108">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="bce2a-109">Notifica al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="bce2a-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bce2a-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="bce2a-110">Requirements</span></span>  
 <span data-ttu-id="bce2a-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bce2a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bce2a-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bce2a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bce2a-113">**.NET Framework versiones:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bce2a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bce2a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="bce2a-114">See also</span></span>

- [<span data-ttu-id="bce2a-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bce2a-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
