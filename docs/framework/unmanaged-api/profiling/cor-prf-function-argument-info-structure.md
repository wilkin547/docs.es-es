---
title: COR_PRF_FUNCTION_ARGUMENT_INFO (Estructura)
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
ms.openlocfilehash: 5feda2ce6dc97576d0b1d4f16ca2b9dd5f3fb05e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718569"
---
# <a name="cor_prf_function_argument_info-structure"></a><span data-ttu-id="e5d17-102">COR_PRF_FUNCTION_ARGUMENT_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="e5d17-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>

<span data-ttu-id="e5d17-103">Representa los argumentos de una función, ordenados de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="e5d17-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5d17-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5d17-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="e5d17-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e5d17-105">Members</span></span>  
  
|<span data-ttu-id="e5d17-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e5d17-106">Member</span></span>|<span data-ttu-id="e5d17-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5d17-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="e5d17-108">El número de bloques de argumentos.</span><span class="sxs-lookup"><span data-stu-id="e5d17-108">The number of blocks of arguments.</span></span> <span data-ttu-id="e5d17-109">Es decir, este valor es el número de estructuras [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) de la `ranges` matriz.</span><span class="sxs-lookup"><span data-stu-id="e5d17-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="e5d17-110">Tamaño total de todos los argumentos.</span><span class="sxs-lookup"><span data-stu-id="e5d17-110">The total size of all arguments.</span></span> <span data-ttu-id="e5d17-111">En otras palabras, este valor es la suma de las longitudes de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="e5d17-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="e5d17-112">Matriz de `COR_PRF_FUNCTION_ARGUMENT_RANGE` estructuras, cada una de las cuales representa un bloque de argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="e5d17-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5d17-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5d17-113">Remarks</span></span>  

 <span data-ttu-id="e5d17-114">Una función puede tener muchos argumentos.</span><span class="sxs-lookup"><span data-stu-id="e5d17-114">A function may have many arguments.</span></span> <span data-ttu-id="e5d17-115">Es posible que esos argumentos no se almacenen de forma contigua en la memoria.</span><span class="sxs-lookup"><span data-stu-id="e5d17-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="e5d17-116">Puede tener un bloque de tres argumentos en un lugar, un bloque de dos argumentos en otro lugar y un bloque final de un argumento en un lugar diferente.</span><span class="sxs-lookup"><span data-stu-id="e5d17-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="e5d17-117">Estos argumentos son todos para la misma función; simplemente se almacenan en distintos lugares.</span><span class="sxs-lookup"><span data-stu-id="e5d17-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="e5d17-118">La `COR_PRF_FUNCTION_ARGUMENT_INFO` estructura representa todos los argumentos de una sola función.</span><span class="sxs-lookup"><span data-stu-id="e5d17-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="e5d17-119">Utiliza una matriz para hacer referencia a todos los bloques de argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="e5d17-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="e5d17-120">Por lo tanto, para una sola función, tiene una única `COR_PRF_FUNCTION_ARGUMENT_INFO` estructura, que hace referencia `COR_PRF_FUNCTION_ARGUMENT_RANGE` a varias estructuras, cada una de las cuales señala a uno o más argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="e5d17-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="e5d17-121">Los argumentos que se almacenan en registros se desbordan en la memoria para compilar las estructuras.</span><span class="sxs-lookup"><span data-stu-id="e5d17-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5d17-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5d17-122">Requirements</span></span>  

 <span data-ttu-id="e5d17-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5d17-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5d17-124">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="e5d17-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e5d17-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5d17-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5d17-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5d17-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d17-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5d17-127">See also</span></span>

- [<span data-ttu-id="e5d17-128">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e5d17-128">Profiling Structures</span></span>](profiling-structures.md)
