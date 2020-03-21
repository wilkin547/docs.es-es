---
title: COR_IL_MAP (Estructura)
ms.date: 03/30/2017
api_name:
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
ms.openlocfilehash: 4c79d0e4e37f3f884651e49c8fff6db72fac4f50
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179292"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="c9580-102">COR_IL_MAP (Estructura)</span><span class="sxs-lookup"><span data-stu-id="c9580-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="c9580-103">Especifica los cambios en el desplazamiento relativo de una función.</span><span class="sxs-lookup"><span data-stu-id="c9580-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9580-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9580-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;
    ULONG32 newOffset;
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="c9580-105">Members</span><span class="sxs-lookup"><span data-stu-id="c9580-105">Members</span></span>  
  
|<span data-ttu-id="c9580-106">Member</span><span class="sxs-lookup"><span data-stu-id="c9580-106">Member</span></span>|<span data-ttu-id="c9580-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9580-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="c9580-108">El antiguo desplazamiento del lenguaje intermedio de Microsoft (MSIL) en relación con el principio de la función.</span><span class="sxs-lookup"><span data-stu-id="c9580-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="c9580-109">El nuevo desplazamiento MSIL en relación con el principio de la función.</span><span class="sxs-lookup"><span data-stu-id="c9580-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="c9580-110">`true`si se sabe que la asignación es precisa; de `false`lo contrario, .</span><span class="sxs-lookup"><span data-stu-id="c9580-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9580-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c9580-111">Remarks</span></span>  
 <span data-ttu-id="c9580-112">El formato de la asignación es el `oldOffset` siguiente: el depurador asumirá que hace referencia a un desplazamiento MSIL dentro del código MSIL original sin modificar.</span><span class="sxs-lookup"><span data-stu-id="c9580-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="c9580-113">El `newOffset` parámetro hace referencia al desplazamiento MSIL correspondiente dentro del nuevo código instrumentado.</span><span class="sxs-lookup"><span data-stu-id="c9580-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="c9580-114">Para que el paso a paso funcione correctamente, se deben cumplir los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="c9580-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="c9580-115">El mapa debe ordenarse en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="c9580-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="c9580-116">El código MSIL instrumentado no se debe reordenar.</span><span class="sxs-lookup"><span data-stu-id="c9580-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="c9580-117">No se debe quitar el código MSIL original.</span><span class="sxs-lookup"><span data-stu-id="c9580-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="c9580-118">El mapa debe incluir entradas para asignar todos los puntos de secuencia del archivo de base de datos de programa (PDB).</span><span class="sxs-lookup"><span data-stu-id="c9580-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="c9580-119">El mapa no interpola las entradas que faltan.</span><span class="sxs-lookup"><span data-stu-id="c9580-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="c9580-120">En el ejemplo siguiente se muestra un mapa y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="c9580-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="c9580-121">Mapa:</span><span class="sxs-lookup"><span data-stu-id="c9580-121">Map:</span></span>  
  
- <span data-ttu-id="c9580-122">0 desplazamiento antiguo, 0 nuevo desplazamiento</span><span class="sxs-lookup"><span data-stu-id="c9580-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="c9580-123">5 desplazamiento antiguo, 10 nuevo desplazamiento</span><span class="sxs-lookup"><span data-stu-id="c9580-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="c9580-124">9 decompensación antigua, 20 nuevos desplazamientos</span><span class="sxs-lookup"><span data-stu-id="c9580-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="c9580-125">Resultados:</span><span class="sxs-lookup"><span data-stu-id="c9580-125">Results:</span></span>  
  
- <span data-ttu-id="c9580-126">Un desplazamiento antiguo de 0, 1, 2, 3 o 4 se asignará a un nuevo desplazamiento de 0.</span><span class="sxs-lookup"><span data-stu-id="c9580-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="c9580-127">Un desplazamiento antiguo de 5, 6, 7 u 8 se asignará al nuevo desplazamiento 10.</span><span class="sxs-lookup"><span data-stu-id="c9580-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="c9580-128">Un desplazamiento antiguo de 9 o superior se asignará al nuevo desplazamiento 20.</span><span class="sxs-lookup"><span data-stu-id="c9580-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="c9580-129">Un nuevo desplazamiento de 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 se asignará al desplazamiento antiguo 0.</span><span class="sxs-lookup"><span data-stu-id="c9580-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="c9580-130">Un nuevo desplazamiento de 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 se asignará al desplazamiento antiguo 5.</span><span class="sxs-lookup"><span data-stu-id="c9580-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="c9580-131">Un nuevo desplazamiento de 20 o superior se asignará al desplazamiento anterior 9.</span><span class="sxs-lookup"><span data-stu-id="c9580-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9580-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9580-132">Requirements</span></span>  
 <span data-ttu-id="c9580-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9580-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9580-134">**Encabezado:** CorDebug.idl, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="c9580-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="c9580-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9580-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9580-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9580-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9580-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c9580-137">See also</span></span>

- [<span data-ttu-id="c9580-138">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="c9580-138">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="c9580-139">Depuración</span><span class="sxs-lookup"><span data-stu-id="c9580-139">Debugging</span></span>](index.md)
