---
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
ms.openlocfilehash: 0210aca5698cd9c86979c13afd1e622b50d194df
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867194"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a><span data-ttu-id="6140e-102">COR_PRF_GC_ROOT_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6140e-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="6140e-103">Indica una propiedad de una raíz de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6140e-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6140e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6140e-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="6140e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="6140e-105">Members</span></span>  
  
|<span data-ttu-id="6140e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="6140e-106">Member</span></span>|<span data-ttu-id="6140e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6140e-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="6140e-108">La raíz impide que una recolección de elementos no utilizados mueva el objeto.</span><span class="sxs-lookup"><span data-stu-id="6140e-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="6140e-109">La raíz no impide la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6140e-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="6140e-110">La raíz hace referencia a un campo del objeto en lugar del propio objeto.</span><span class="sxs-lookup"><span data-stu-id="6140e-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="6140e-111">La raíz evita la recolección de elementos no utilizados si el recuento de referencias del objeto es un determinado valor.</span><span class="sxs-lookup"><span data-stu-id="6140e-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6140e-112">Notas</span><span class="sxs-lookup"><span data-stu-id="6140e-112">Remarks</span></span>  
 <span data-ttu-id="6140e-113">`COR_PRF_GC_ROOT_FLAGS` es una máscara de datos que proporciona información adicional sobre raíces especiales.</span><span class="sxs-lookup"><span data-stu-id="6140e-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="6140e-114">Sin embargo, no todas las raíces son especiales.</span><span class="sxs-lookup"><span data-stu-id="6140e-114">However, not all roots are special.</span></span> <span data-ttu-id="6140e-115">Por ejemplo, algunas raíces no son referencias débiles, punteros interiores, ancladas o con recuento de referencias.</span><span class="sxs-lookup"><span data-stu-id="6140e-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="6140e-116">Para tales raíces, no hay marcas para transmitir.</span><span class="sxs-lookup"><span data-stu-id="6140e-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="6140e-117">Por lo tanto, los métodos que utilizan esta enumeración, como el método [ICorProfilerCallback2:: RootReferences2 (](icorprofilercallback2-rootreferences2-method.md) , envían 0 para la máscara de máscara de marcas, lo que indica que todas las marcas están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="6140e-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6140e-118">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6140e-118">Requirements</span></span>  
 <span data-ttu-id="6140e-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6140e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6140e-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6140e-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6140e-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6140e-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6140e-122">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6140e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6140e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6140e-123">See also</span></span>

- [<span data-ttu-id="6140e-124">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="6140e-124">Profiling Enumerations</span></span>](profiling-enumerations.md)
