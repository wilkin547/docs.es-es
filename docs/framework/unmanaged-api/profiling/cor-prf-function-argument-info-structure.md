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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 658b88349bedcbcefd0b97226c7bd1fa34f656c7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781922"
---
# <a name="corprffunctionargumentinfo-structure"></a><span data-ttu-id="9f6b9-102">COR_PRF_FUNCTION_ARGUMENT_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="9f6b9-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="9f6b9-103">Representa los argumentos de una función, ordenados de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="9f6b9-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f6b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f6b9-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="9f6b9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9f6b9-105">Members</span></span>  
  
|<span data-ttu-id="9f6b9-106">Member</span><span class="sxs-lookup"><span data-stu-id="9f6b9-106">Member</span></span>|<span data-ttu-id="9f6b9-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9f6b9-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="9f6b9-108">El número de bloques de argumentos.</span><span class="sxs-lookup"><span data-stu-id="9f6b9-108">The number of blocks of arguments.</span></span> <span data-ttu-id="9f6b9-109">Es decir, este valor es el número de [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) estructuras en el `ranges` matriz.</span><span class="sxs-lookup"><span data-stu-id="9f6b9-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="9f6b9-110">El tamaño total de todos los argumentos.</span><span class="sxs-lookup"><span data-stu-id="9f6b9-110">The total size of all arguments.</span></span> <span data-ttu-id="9f6b9-111">En otras palabras, este valor es la suma de las longitudes de argumento.</span><span class="sxs-lookup"><span data-stu-id="9f6b9-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="9f6b9-112">Una matriz de `COR_PRF_FUNCTION_ARGUMENT_RANGE` estructuras, cada uno de los cuales representa un bloque de argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="9f6b9-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f6b9-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9f6b9-113">Remarks</span></span>  
 <span data-ttu-id="9f6b9-114">Una función puede tener muchos argumentos.</span><span class="sxs-lookup"><span data-stu-id="9f6b9-114">A function may have many arguments.</span></span> <span data-ttu-id="9f6b9-115">Estos argumentos no podrían almacenarse de forma contigua en la memoria.</span><span class="sxs-lookup"><span data-stu-id="9f6b9-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="9f6b9-116">Podría tener un bloque de tres argumentos en un solo lugar, un bloque de dos argumentos en otro lugar y un bloque final de un argumento en un lugar diferente.</span><span class="sxs-lookup"><span data-stu-id="9f6b9-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="9f6b9-117">Estos argumentos son todas de la misma función; simplemente se almacenan en distintos lugares.</span><span class="sxs-lookup"><span data-stu-id="9f6b9-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="9f6b9-118">El `COR_PRF_FUNCTION_ARGUMENT_INFO` estructura representa todos los argumentos de una sola función.</span><span class="sxs-lookup"><span data-stu-id="9f6b9-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="9f6b9-119">Usa una matriz para hacer referencia a todos los bloques de argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="9f6b9-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="9f6b9-120">Por lo tanto, para una sola función, tiene una sola `COR_PRF_FUNCTION_ARGUMENT_INFO` estructura, que hace referencia a varios `COR_PRF_FUNCTION_ARGUMENT_RANGE` estructuras, cada uno de los cuales señala a uno o más argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="9f6b9-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="9f6b9-121">Argumentos que se almacenan en los registros se vuelcan en la memoria para crear las estructuras.</span><span class="sxs-lookup"><span data-stu-id="9f6b9-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f6b9-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f6b9-122">Requirements</span></span>  
 <span data-ttu-id="9f6b9-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f6b9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f6b9-124">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="9f6b9-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="9f6b9-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f6b9-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f6b9-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f6b9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f6b9-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f6b9-127">See also</span></span>

- [<span data-ttu-id="9f6b9-128">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9f6b9-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
