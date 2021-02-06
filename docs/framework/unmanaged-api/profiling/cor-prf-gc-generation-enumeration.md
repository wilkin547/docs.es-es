---
description: 'Más información acerca de: enumeración COR_PRF_GC_GENERATION'
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
ms.openlocfilehash: 108bb4b2b4cba57235d354efe3b815a0e0df17ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648940"
---
# <a name="cor_prf_gc_generation-enumeration"></a><span data-ttu-id="81bbc-103">COR_PRF_GC_GENERATION (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="81bbc-103">COR_PRF_GC_GENERATION Enumeration</span></span>

<span data-ttu-id="81bbc-104">Identifica una generación de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="81bbc-104">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81bbc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81bbc-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3,
    COR_PRF_GC_PINNED_OBJECT_HEAP= 4
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="81bbc-106">Members</span><span class="sxs-lookup"><span data-stu-id="81bbc-106">Members</span></span>  
  
|<span data-ttu-id="81bbc-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="81bbc-107">Member</span></span>|<span data-ttu-id="81bbc-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="81bbc-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="81bbc-109">El objeto se almacena como generación 0.</span><span class="sxs-lookup"><span data-stu-id="81bbc-109">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="81bbc-110">El objeto se almacena como generación 1.</span><span class="sxs-lookup"><span data-stu-id="81bbc-110">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="81bbc-111">El objeto se almacena como generación 2.</span><span class="sxs-lookup"><span data-stu-id="81bbc-111">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="81bbc-112">El objeto se almacena en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="81bbc-112">The object is stored in the large-object heap.</span></span>|  
|`COR_PRF_GC_PINNED_OBJECT_HEAP`|<span data-ttu-id="81bbc-113">El objeto se almacena en el montón de objetos anclados.</span><span class="sxs-lookup"><span data-stu-id="81bbc-113">The object is stored in the pinned-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81bbc-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="81bbc-114">Remarks</span></span>  

 <span data-ttu-id="81bbc-115">El recolector de elementos no utilizados mejora el rendimiento de la administración de memoria dividiendo los objetos en generaciones en función de la edad.</span><span class="sxs-lookup"><span data-stu-id="81bbc-115">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="81bbc-116">El recolector de elementos no utilizados usa actualmente tres generaciones, numeradas como 0, 1 y 2, y dos segmentos de montón especiales, uno para objetos grandes y otro para objetos anclados.</span><span class="sxs-lookup"><span data-stu-id="81bbc-116">The garbage collector currently uses three generations, numbered 0, 1, and 2, and two special heap segments, one for large objects and one for pinned objects.</span></span>
  
 <span data-ttu-id="81bbc-117">Los objetos cuyo tamaño es mayor que un valor de umbral se almacenan en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="81bbc-117">Objects whose size is larger than a threshold value are stored in the large-object heap.</span></span> <span data-ttu-id="81bbc-118">Los objetos anclados se pueden asignar al montón de objetos anclados para evitar el costo de rendimiento de asignarlos en los montones normales.</span><span class="sxs-lookup"><span data-stu-id="81bbc-118">Pinned objects can be allocated to the pinned-object heap to avoid the performance cost of allocating them on the normal heaps.</span></span> <span data-ttu-id="81bbc-119">Otros objetos asignados empiezan fuera de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="81bbc-119">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="81bbc-120">Todos los objetos que existen después de la recolección de elementos no utilizados en la generación 0 se promueven a la generación 1.</span><span class="sxs-lookup"><span data-stu-id="81bbc-120">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="81bbc-121">Los objetos que existen después de la recolección de elementos no utilizados se producen en la generación 1 se mueven a la generación 2.</span><span class="sxs-lookup"><span data-stu-id="81bbc-121">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="81bbc-122">El uso de generaciones significa que el recolector de elementos no utilizados tiene que trabajar solo con un subconjunto de los objetos asignados en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="81bbc-122">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="81bbc-123">`COR_PRF_GC_GENERATION`La estructura de [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) usa la enumeración.</span><span class="sxs-lookup"><span data-stu-id="81bbc-123">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81bbc-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81bbc-124">Requirements</span></span>  

 <span data-ttu-id="81bbc-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81bbc-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81bbc-126">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="81bbc-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="81bbc-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81bbc-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81bbc-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81bbc-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81bbc-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="81bbc-129">See also</span></span>

- [<span data-ttu-id="81bbc-130">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="81bbc-130">Profiling Enumerations</span></span>](profiling-enumerations.md)
