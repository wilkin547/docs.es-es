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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f179e3b01d6c3b34dfa765565a0fc38d0ba867c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753698"
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="0130d-102">COR_PRF_GC_ROOT_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0130d-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="0130d-103">Indica una propiedad de una raíz de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0130d-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0130d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0130d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="0130d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0130d-105">Members</span></span>  
  
|<span data-ttu-id="0130d-106">Member</span><span class="sxs-lookup"><span data-stu-id="0130d-106">Member</span></span>|<span data-ttu-id="0130d-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0130d-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="0130d-108">La raíz impide que una colección de elementos no utilizados traslade el objeto.</span><span class="sxs-lookup"><span data-stu-id="0130d-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="0130d-109">La raíz no impide la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="0130d-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="0130d-110">La raíz hace referencia a un campo de objeto en lugar del propio objeto.</span><span class="sxs-lookup"><span data-stu-id="0130d-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="0130d-111">La raíz impide la recolección si el recuento de referencias del objeto es un valor determinado.</span><span class="sxs-lookup"><span data-stu-id="0130d-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0130d-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0130d-112">Remarks</span></span>  
 <span data-ttu-id="0130d-113">`COR_PRF_GC_ROOT_FLAGS` es una máscara de bits que proporciona información adicional sobre raíces especiales.</span><span class="sxs-lookup"><span data-stu-id="0130d-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="0130d-114">Sin embargo, no todas las raíces son especiales.</span><span class="sxs-lookup"><span data-stu-id="0130d-114">However, not all roots are special.</span></span> <span data-ttu-id="0130d-115">Por ejemplo, algunas raíces no son referencias débiles, punteros interiores, anclados o recuento de referencias.</span><span class="sxs-lookup"><span data-stu-id="0130d-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="0130d-116">Para esas raíces, no hay ninguna marca para transmitir.</span><span class="sxs-lookup"><span data-stu-id="0130d-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="0130d-117">Por lo tanto, los métodos que utilizan esta enumeración, como el [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) método send 0 para la máscara de bits de marcas, que indica que todos los marcadores están desactivados.</span><span class="sxs-lookup"><span data-stu-id="0130d-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0130d-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0130d-118">Requirements</span></span>  
 <span data-ttu-id="0130d-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0130d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0130d-120">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0130d-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0130d-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0130d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0130d-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0130d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0130d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0130d-123">See also</span></span>

- [<span data-ttu-id="0130d-124">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0130d-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
