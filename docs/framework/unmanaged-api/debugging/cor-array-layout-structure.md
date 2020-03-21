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
ms.openlocfilehash: ca2d00611a7530dfb0d1c2a27123947bdf69820d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179353"
---
# <a name="cor_array_layout-structure"></a><span data-ttu-id="b226a-102">COR_ARRAY_LAYOUT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="b226a-102">COR_ARRAY_LAYOUT Structure</span></span>
<span data-ttu-id="b226a-103">Proporciona información sobre la distribución de un objeto de matriz en la memoria.</span><span class="sxs-lookup"><span data-stu-id="b226a-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b226a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b226a-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b226a-105">Members</span><span class="sxs-lookup"><span data-stu-id="b226a-105">Members</span></span>  
  
|<span data-ttu-id="b226a-106">Member</span><span class="sxs-lookup"><span data-stu-id="b226a-106">Member</span></span>|<span data-ttu-id="b226a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b226a-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="b226a-108">Identificador del tipo de objetos que contiene la matriz.</span><span class="sxs-lookup"><span data-stu-id="b226a-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="b226a-109">Un corElementType valor de enumeración que indica si el componente es una referencia de recolección de elementos no utilizados, una clase de valor o una primitiva.</span><span class="sxs-lookup"><span data-stu-id="b226a-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="b226a-110">Desplazamiento al primer elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b226a-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="b226a-111">El tamaño de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="b226a-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="b226a-112">Desplazamiento al número de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b226a-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="b226a-113">El tamaño del rango, en bytes.</span><span class="sxs-lookup"><span data-stu-id="b226a-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="b226a-114">El número de rangos en la matriz.</span><span class="sxs-lookup"><span data-stu-id="b226a-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="b226a-115">Desplazamiento en el que comienzan los rangos.</span><span class="sxs-lookup"><span data-stu-id="b226a-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b226a-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b226a-116">Remarks</span></span>  
 <span data-ttu-id="b226a-117">El `rankSize` campo especifica el tamaño de un rango en una matriz multidimensional.</span><span class="sxs-lookup"><span data-stu-id="b226a-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="b226a-118">También es preciso para matrices unidimensionales.</span><span class="sxs-lookup"><span data-stu-id="b226a-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="b226a-119">El valor `numRanks` de es 1 para `N` una matriz unidimensional `N` y para una matriz multidimensional de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="b226a-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b226a-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b226a-120">Requirements</span></span>  
 <span data-ttu-id="b226a-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b226a-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b226a-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b226a-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b226a-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b226a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b226a-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b226a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b226a-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b226a-125">See also</span></span>

- [<span data-ttu-id="b226a-126">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="b226a-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="b226a-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="b226a-127">Debugging</span></span>](index.md)
