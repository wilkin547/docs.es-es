---
description: 'Más información acerca de: ICorProfilerInfo:: Forcegc ((método)'
title: ICorProfilerInfo::ForceGC (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
ms.openlocfilehash: 1abed09450b72730a11a168223b6da05e9baf9be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737550"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="e285f-103">ICorProfilerInfo::ForceGC (Método)</span><span class="sxs-lookup"><span data-stu-id="e285f-103">ICorProfilerInfo::ForceGC Method</span></span>

<span data-ttu-id="e285f-104">Fuerza la recolección de elementos no utilizados en el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e285f-104">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e285f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e285f-105">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e285f-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e285f-106">Remarks</span></span>  

 <span data-ttu-id="e285f-107">`ForceGC`Solo se debe llamar al método desde un subproceso que nunca ha ejecutado código administrado y no tiene ninguna devolución de llamada del generador de perfiles en su pila.</span><span class="sxs-lookup"><span data-stu-id="e285f-107">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="e285f-108">La implementación más cómoda es crear un subproceso independiente en el generador de perfiles que llama a `ForceGC` cuando se señala.</span><span class="sxs-lookup"><span data-stu-id="e285f-108">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e285f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e285f-109">Requirements</span></span>  

 <span data-ttu-id="e285f-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e285f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e285f-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e285f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e285f-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e285f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e285f-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e285f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e285f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e285f-114">See also</span></span>

- [<span data-ttu-id="e285f-115">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e285f-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
