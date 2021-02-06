---
description: 'Más información acerca de: enumeración COR_PRF_GC_ROOT_FLAGS'
title: COR_PRF_GC_ROOT_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
ms.openlocfilehash: 6d566ed5ac1d0b4e15a855fbbb8a0fca3a5a429e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648823"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a><span data-ttu-id="00ad4-103">COR_PRF_GC_ROOT_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="00ad4-103">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>

<span data-ttu-id="00ad4-104">Indica una propiedad de una raíz de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="00ad4-104">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00ad4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00ad4-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="00ad4-106">Members</span><span class="sxs-lookup"><span data-stu-id="00ad4-106">Members</span></span>  
  
|<span data-ttu-id="00ad4-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="00ad4-107">Member</span></span>|<span data-ttu-id="00ad4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="00ad4-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="00ad4-109">La raíz impide que una recolección de elementos no utilizados mueva el objeto.</span><span class="sxs-lookup"><span data-stu-id="00ad4-109">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="00ad4-110">La raíz no impide la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="00ad4-110">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="00ad4-111">La raíz hace referencia a un campo del objeto en lugar del propio objeto.</span><span class="sxs-lookup"><span data-stu-id="00ad4-111">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="00ad4-112">La raíz evita la recolección de elementos no utilizados si el recuento de referencias del objeto es un determinado valor.</span><span class="sxs-lookup"><span data-stu-id="00ad4-112">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00ad4-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="00ad4-113">Remarks</span></span>  

 <span data-ttu-id="00ad4-114">`COR_PRF_GC_ROOT_FLAGS` es una máscara de máscara que proporciona información adicional sobre raíces especiales.</span><span class="sxs-lookup"><span data-stu-id="00ad4-114">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="00ad4-115">Sin embargo, no todas las raíces son especiales.</span><span class="sxs-lookup"><span data-stu-id="00ad4-115">However, not all roots are special.</span></span> <span data-ttu-id="00ad4-116">Por ejemplo, algunas raíces no son referencias débiles, punteros interiores, ancladas o con recuento de referencias.</span><span class="sxs-lookup"><span data-stu-id="00ad4-116">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="00ad4-117">Para tales raíces, no hay marcas para transmitir.</span><span class="sxs-lookup"><span data-stu-id="00ad4-117">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="00ad4-118">Por lo tanto, los métodos que utilizan esta enumeración, como el método [ICorProfilerCallback2:: RootReferences2 (](icorprofilercallback2-rootreferences2-method.md) , envían 0 para la máscara de máscara de marcas, lo que indica que todas las marcas están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="00ad4-118">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00ad4-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00ad4-119">Requirements</span></span>  

 <span data-ttu-id="00ad4-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00ad4-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00ad4-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="00ad4-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="00ad4-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00ad4-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00ad4-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00ad4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ad4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="00ad4-124">See also</span></span>

- [<span data-ttu-id="00ad4-125">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="00ad4-125">Profiling Enumerations</span></span>](profiling-enumerations.md)
