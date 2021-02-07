---
description: 'Más información acerca de: estructura de COR_SEGMENT'
title: COR_SEGMENT (Estructura)
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
ms.openlocfilehash: 9bbc452b2c2036d019175ac1be8b9917ffa07b6a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712199"
---
# <a name="cor_segment-structure"></a><span data-ttu-id="f8226-103">COR_SEGMENT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="f8226-103">COR_SEGMENT Structure</span></span>

<span data-ttu-id="f8226-104">Contiene información sobre una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="f8226-104">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8226-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8226-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;
    CORDB_ADDRESS end;
    CorDebugGenerationTypes gen;
    ULONG heap;
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="f8226-106">Members</span><span class="sxs-lookup"><span data-stu-id="f8226-106">Members</span></span>  
  
|<span data-ttu-id="f8226-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="f8226-107">Member</span></span>|<span data-ttu-id="f8226-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8226-108">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="f8226-109">La dirección de inicio de la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="f8226-109">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="f8226-110">La dirección final de la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="f8226-110">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="f8226-111">Un miembro de la enumeración [CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md) que indica la generación de la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="f8226-111">A [CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="f8226-112">El número de montón en el que reside la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="f8226-112">The heap number in which the memory region resides.</span></span> <span data-ttu-id="f8226-113">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f8226-113">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8226-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f8226-114">Remarks</span></span>  

 <span data-ttu-id="f8226-115">La estructura `COR_SEGMENTS` representa una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="f8226-115">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="f8226-116">Los objetos `COR_SEGMENTS` son miembros del objeto de colección [ICorDebugHeapRegionEnum](icordebugheapsegmentenum-interface.md), que se rellena mediante una llamada al método [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md).</span><span class="sxs-lookup"><span data-stu-id="f8226-116">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="f8226-117">El campo `heap` es el número de procesador, que se corresponde con el montón que se va a notificar.</span><span class="sxs-lookup"><span data-stu-id="f8226-117">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="f8226-118">Para los recolectores de elementos no utilizados de la estación de trabajo, su valor siempre es cero, porque las estaciones de trabajo tienen solo un montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f8226-118">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="f8226-119">Para los recolectores de elementos no utilizados de servidor, su valor se corresponde con el procesador al que está vinculado el montón.</span><span class="sxs-lookup"><span data-stu-id="f8226-119">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="f8226-120">Tenga en cuenta que podría haber más o menos montones de recolección de elementos no utilizados que procesadores reales debido a los detalles de implementación del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f8226-120">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8226-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8226-121">Requirements</span></span>  

 <span data-ttu-id="f8226-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8226-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8226-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8226-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8226-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8226-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8226-125">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8226-125">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8226-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8226-126">See also</span></span>

- [<span data-ttu-id="f8226-127">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="f8226-127">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="f8226-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="f8226-128">Debugging</span></span>](index.md)
