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
ms.openlocfilehash: 2ca6c89a671c4d7882e7cefdb820d07ac5636530
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727411"
---
# <a name="cor_array_layout-structure"></a><span data-ttu-id="c1126-102">COR_ARRAY_LAYOUT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="c1126-102">COR_ARRAY_LAYOUT Structure</span></span>

<span data-ttu-id="c1126-103">Proporciona información sobre la distribución de un objeto de matriz en la memoria.</span><span class="sxs-lookup"><span data-stu-id="c1126-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1126-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1126-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c1126-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c1126-105">Members</span></span>  
  
|<span data-ttu-id="c1126-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c1126-106">Member</span></span>|<span data-ttu-id="c1126-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1126-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="c1126-108">Identificador del tipo de objetos que contiene la matriz.</span><span class="sxs-lookup"><span data-stu-id="c1126-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="c1126-109">Un valor de enumeración de CorElementType que indica si el componente es una referencia de recolección de elementos no utilizados, una clase de valor o un primitivo.</span><span class="sxs-lookup"><span data-stu-id="c1126-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="c1126-110">Desplazamiento al primer elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="c1126-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="c1126-111">Tamaño de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="c1126-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="c1126-112">Desplazamiento al número de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="c1126-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="c1126-113">Tamaño del rango, en bytes.</span><span class="sxs-lookup"><span data-stu-id="c1126-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="c1126-114">Número de rangos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="c1126-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="c1126-115">Desplazamiento en el que se inician los rangos.</span><span class="sxs-lookup"><span data-stu-id="c1126-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1126-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1126-116">Remarks</span></span>  

 <span data-ttu-id="c1126-117">El `rankSize` campo especifica el tamaño de un rango en una matriz multidimensional.</span><span class="sxs-lookup"><span data-stu-id="c1126-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="c1126-118">También es preciso para las matrices unidimensionales.</span><span class="sxs-lookup"><span data-stu-id="c1126-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="c1126-119">El valor de `numRanks` es 1 para una matriz unidimensional y `N` para una matriz multidimensional de `N` dimensiones.</span><span class="sxs-lookup"><span data-stu-id="c1126-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1126-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1126-120">Requirements</span></span>  

 <span data-ttu-id="c1126-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1126-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1126-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1126-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1126-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1126-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1126-124">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1126-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1126-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1126-125">See also</span></span>

- [<span data-ttu-id="c1126-126">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="c1126-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="c1126-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="c1126-127">Debugging</span></span>](index.md)
