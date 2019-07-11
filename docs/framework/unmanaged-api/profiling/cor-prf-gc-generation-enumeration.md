---
title: COR_PRF_GC_GENERATION (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74e70f58600205d44a9ba052981b2cc67b3a44ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753809"
---
# <a name="corprfgcgeneration-enumeration"></a><span data-ttu-id="eb03d-102">COR_PRF_GC_GENERATION (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb03d-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="eb03d-103">Identifica una colección de elementos no utilizados de generación.</span><span class="sxs-lookup"><span data-stu-id="eb03d-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb03d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb03d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="eb03d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="eb03d-105">Members</span></span>  
  
|<span data-ttu-id="eb03d-106">Member</span><span class="sxs-lookup"><span data-stu-id="eb03d-106">Member</span></span>|<span data-ttu-id="eb03d-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="eb03d-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="eb03d-108">El objeto se almacena como generación 0.</span><span class="sxs-lookup"><span data-stu-id="eb03d-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="eb03d-109">El objeto se almacena como generación 1.</span><span class="sxs-lookup"><span data-stu-id="eb03d-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="eb03d-110">El objeto se almacena como generación 2.</span><span class="sxs-lookup"><span data-stu-id="eb03d-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="eb03d-111">El objeto se almacena en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="eb03d-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb03d-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eb03d-112">Remarks</span></span>  
 <span data-ttu-id="eb03d-113">El recolector de elementos no utilizados mejora el rendimiento de la administración de memoria dividiendo los objetos en las generaciones según la edad.</span><span class="sxs-lookup"><span data-stu-id="eb03d-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="eb03d-114">El recolector de elementos no utilizados utiliza actualmente tres generaciones, numeradas de 0, 1 y 2, además de un segmento de montón especial que se usa para los objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="eb03d-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="eb03d-115">Los objetos cuyo tamaño es mayor que un valor determinado se almacenan en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="eb03d-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="eb03d-116">Para empezar otros objetos asignados que pertenecen a la generación 0.</span><span class="sxs-lookup"><span data-stu-id="eb03d-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="eb03d-117">Todos los objetos que existen después de que se produce una recolección en la generación 0 se promueven a la generación 1.</span><span class="sxs-lookup"><span data-stu-id="eb03d-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="eb03d-118">Mueven los objetos que existen después de que se produce una recolección de generación 1 a la generación 2.</span><span class="sxs-lookup"><span data-stu-id="eb03d-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="eb03d-119">El uso de las generaciones significa que el recolector de elementos no utilizados tiene que trabajar con solo un subconjunto de los objetos asignados en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="eb03d-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="eb03d-120">El `COR_PRF_GC_GENERATION` enumeración la utiliza el [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="eb03d-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb03d-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb03d-121">Requirements</span></span>  
 <span data-ttu-id="eb03d-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb03d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb03d-123">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eb03d-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eb03d-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb03d-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb03d-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb03d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb03d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb03d-126">See also</span></span>

- [<span data-ttu-id="eb03d-127">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="eb03d-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
