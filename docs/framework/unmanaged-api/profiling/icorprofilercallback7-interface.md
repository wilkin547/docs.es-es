---
description: 'Más información acerca de: interfaz ICorProfilerCallback7'
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
ms.openlocfilehash: 3db402db221fca4487939f9817b20ec0c5207fc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781745"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="cf23e-103">Interfaz ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="cf23e-103">ICorProfilerCallback7 Interface</span></span>

<span data-ttu-id="cf23e-104">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="cf23e-104">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="cf23e-105">Una subclase de [ICorProfilerCallback6](icorprofilercallback6-interface.md) que proporciona un método de devolución de llamada que Common Language Runtime utiliza para notificar al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="cf23e-105">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cf23e-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="cf23e-106">Methods</span></span>  
  
|<span data-ttu-id="cf23e-107">Método</span><span class="sxs-lookup"><span data-stu-id="cf23e-107">Method</span></span>|<span data-ttu-id="cf23e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf23e-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cf23e-109">Método ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="cf23e-109">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="cf23e-110">Notifica al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="cf23e-110">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cf23e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf23e-111">Requirements</span></span>  

 <span data-ttu-id="cf23e-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf23e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf23e-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf23e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf23e-114">**.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf23e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf23e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf23e-115">See also</span></span>

- [<span data-ttu-id="cf23e-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="cf23e-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
