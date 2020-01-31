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
ms.openlocfilehash: 4eff8472e353c4e5fd2505b281cc9efc89f013fc
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867222"
---
# <a name="cor_prf_gc_generation-enumeration"></a><span data-ttu-id="4535b-102">COR_PRF_GC_GENERATION (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4535b-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="4535b-103">Identifica una generación de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4535b-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4535b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4535b-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="4535b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4535b-105">Members</span></span>  
  
|<span data-ttu-id="4535b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4535b-106">Member</span></span>|<span data-ttu-id="4535b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4535b-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="4535b-108">El objeto se almacena como generación 0.</span><span class="sxs-lookup"><span data-stu-id="4535b-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="4535b-109">El objeto se almacena como generación 1.</span><span class="sxs-lookup"><span data-stu-id="4535b-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="4535b-110">El objeto se almacena como generación 2.</span><span class="sxs-lookup"><span data-stu-id="4535b-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="4535b-111">El objeto se almacena en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="4535b-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4535b-112">Notas</span><span class="sxs-lookup"><span data-stu-id="4535b-112">Remarks</span></span>  
 <span data-ttu-id="4535b-113">El recolector de elementos no utilizados mejora el rendimiento de la administración de memoria dividiendo los objetos en generaciones en función de la edad.</span><span class="sxs-lookup"><span data-stu-id="4535b-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="4535b-114">El recolector de elementos no utilizados usa actualmente tres generaciones, numeradas como 0, 1 y 2, además de un segmento de montón especial que se utiliza para objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="4535b-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="4535b-115">Los objetos cuyo tamaño es mayor que un valor determinado se almacenan en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="4535b-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="4535b-116">Otros objetos asignados empiezan fuera de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="4535b-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="4535b-117">Todos los objetos que existen después de la recolección de elementos no utilizados en la generación 0 se promueven a la generación 1.</span><span class="sxs-lookup"><span data-stu-id="4535b-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="4535b-118">Los objetos que existen después de la recolección de elementos no utilizados se producen en la generación 1 se mueven a la generación 2.</span><span class="sxs-lookup"><span data-stu-id="4535b-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="4535b-119">El uso de generaciones significa que el recolector de elementos no utilizados tiene que trabajar solo con un subconjunto de los objetos asignados en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="4535b-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="4535b-120">La estructura de [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) utiliza la enumeración `COR_PRF_GC_GENERATION`.</span><span class="sxs-lookup"><span data-stu-id="4535b-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4535b-121">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4535b-121">Requirements</span></span>  
 <span data-ttu-id="4535b-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4535b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4535b-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4535b-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4535b-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4535b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4535b-125">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4535b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4535b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4535b-126">See also</span></span>

- [<span data-ttu-id="4535b-127">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4535b-127">Profiling Enumerations</span></span>](profiling-enumerations.md)
