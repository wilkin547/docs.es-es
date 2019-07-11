---
title: COR_ARRAY_LAYOUT (Estructura)
ms.date: 03/30/2017
api_name:
- COR_ARRAY_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ARRAY_LAYOUT
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cccb862a0dfd16eb0bbfe557e3c35373cd7e7b8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740811"
---
# <a name="corarraylayout-structure"></a><span data-ttu-id="053c6-102">COR_ARRAY_LAYOUT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="053c6-102">COR_ARRAY_LAYOUT Structure</span></span>
<span data-ttu-id="053c6-103">Proporciona información sobre la distribución de un objeto de matriz en la memoria.</span><span class="sxs-lookup"><span data-stu-id="053c6-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="053c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="053c6-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;   
    ULONG32 rankSize;   
    ULONG32 numRanks;   
    ULONG32 rankOffset;   
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="053c6-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="053c6-105">Members</span></span>  
  
|<span data-ttu-id="053c6-106">Member</span><span class="sxs-lookup"><span data-stu-id="053c6-106">Member</span></span>|<span data-ttu-id="053c6-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="053c6-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="053c6-108">El identificador del tipo de objetos que contiene la matriz.</span><span class="sxs-lookup"><span data-stu-id="053c6-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="053c6-109">Un valor de enumeración CorElementType que indica si el componente es un tipo primitivo, una clase de valor o una referencia de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="053c6-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="053c6-110">El desplazamiento al primer elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="053c6-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="053c6-111">El tamaño de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="053c6-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="053c6-112">El desplazamiento en el número de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="053c6-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="053c6-113">El tamaño de la clasificación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="053c6-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="053c6-114">El número de rangos en la matriz.</span><span class="sxs-lookup"><span data-stu-id="053c6-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="053c6-115">El desplazamiento en el que iniciar los rangos.</span><span class="sxs-lookup"><span data-stu-id="053c6-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="053c6-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="053c6-116">Remarks</span></span>  
 <span data-ttu-id="053c6-117">El `rankSize` campo especifica el tamaño de un rango en una matriz multidimensional.</span><span class="sxs-lookup"><span data-stu-id="053c6-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="053c6-118">Es preciso para las matrices unidimensionales también.</span><span class="sxs-lookup"><span data-stu-id="053c6-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="053c6-119">El valor de `numRanks` es 1 para una matriz unidimensional y `N` para una matriz multidimensional de `N` dimensiones.</span><span class="sxs-lookup"><span data-stu-id="053c6-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="053c6-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="053c6-120">Requirements</span></span>  
 <span data-ttu-id="053c6-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="053c6-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="053c6-122">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="053c6-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="053c6-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="053c6-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="053c6-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="053c6-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="053c6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="053c6-125">See also</span></span>

- [<span data-ttu-id="053c6-126">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="053c6-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="053c6-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="053c6-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
