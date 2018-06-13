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
ms.openlocfilehash: 8283139566050b1858a003316dc46581822a9bbb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450159"
---
# <a name="corprfgcgeneration-enumeration"></a><span data-ttu-id="548a9-102">COR_PRF_GC_GENERATION (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="548a9-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="548a9-103">Identifica la generación de una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="548a9-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="548a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="548a9-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="548a9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="548a9-105">Members</span></span>  
  
|<span data-ttu-id="548a9-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="548a9-106">Member</span></span>|<span data-ttu-id="548a9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="548a9-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="548a9-108">El objeto se almacena como generación 0.</span><span class="sxs-lookup"><span data-stu-id="548a9-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="548a9-109">El objeto se almacena como generación 1.</span><span class="sxs-lookup"><span data-stu-id="548a9-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="548a9-110">El objeto se almacena como generación 2.</span><span class="sxs-lookup"><span data-stu-id="548a9-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="548a9-111">El objeto se almacena en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="548a9-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="548a9-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="548a9-112">Remarks</span></span>  
 <span data-ttu-id="548a9-113">El recolector de elementos no utilizados mejora el rendimiento de la administración de memoria dividiendo los objetos en las generaciones según la edad.</span><span class="sxs-lookup"><span data-stu-id="548a9-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="548a9-114">El recolector de elementos no utilizados utiliza actualmente tres generaciones numeradas de 0, 1 y 2, además de un segmento de montón especial que se utiliza para los objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="548a9-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="548a9-115">Los objetos cuyo tamaño es mayor que un valor determinado se almacenan en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="548a9-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="548a9-116">Otros objetos asignados empiezan perteneciendo a la generación 0.</span><span class="sxs-lookup"><span data-stu-id="548a9-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="548a9-117">Todos los objetos que existen después de recolección de elementos no utilizados se produce en la generación 0 se promueven a la generación 1.</span><span class="sxs-lookup"><span data-stu-id="548a9-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="548a9-118">Mueven los objetos que existen después de que se realiza una recolección de la generación 1 a la generación 2.</span><span class="sxs-lookup"><span data-stu-id="548a9-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="548a9-119">El uso de generaciones significa que el recolector de elementos no utilizados tiene que trabajar con solo un subconjunto de los objetos asignados en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="548a9-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="548a9-120">El `COR_PRF_GC_GENERATION` enumeración es utilizada por la [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="548a9-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="548a9-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="548a9-121">Requirements</span></span>  
 <span data-ttu-id="548a9-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="548a9-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="548a9-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="548a9-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="548a9-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="548a9-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="548a9-125">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="548a9-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="548a9-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="548a9-126">See Also</span></span>  
 [<span data-ttu-id="548a9-127">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="548a9-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
