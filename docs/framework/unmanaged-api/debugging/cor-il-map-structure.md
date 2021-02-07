---
description: 'Más información acerca de: estructura de COR_IL_MAP'
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
ms.openlocfilehash: ff3d636429f51119342baea5d71163eb9d764e03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712329"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="5e9cc-103">COR_IL_MAP (Estructura)</span><span class="sxs-lookup"><span data-stu-id="5e9cc-103">COR_IL_MAP Structure</span></span>

<span data-ttu-id="5e9cc-104">Especifica los cambios en el desplazamiento relativo de una función.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-104">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e9cc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e9cc-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;
    ULONG32 newOffset;
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="5e9cc-106">Members</span><span class="sxs-lookup"><span data-stu-id="5e9cc-106">Members</span></span>  
  
|<span data-ttu-id="5e9cc-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="5e9cc-107">Member</span></span>|<span data-ttu-id="5e9cc-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e9cc-108">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="5e9cc-109">El desplazamiento anterior del lenguaje intermedio de Microsoft (MSIL) con respecto al principio de la función.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-109">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="5e9cc-110">Nuevo desplazamiento de MSIL relativo al principio de la función.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-110">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="5e9cc-111">`true` Si se sabe que la asignación es precisa; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="5e9cc-111">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e9cc-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5e9cc-112">Remarks</span></span>  

 <span data-ttu-id="5e9cc-113">El formato del mapa es el siguiente: el depurador asumirá que `oldOffset` hace referencia a un desplazamiento de MSIL en el código MSIL original y sin modificar.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-113">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="5e9cc-114">El `newOffset` parámetro hace referencia al desplazamiento de MSIL correspondiente en el nuevo código instrumentado.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-114">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="5e9cc-115">Para que funcione correctamente, deben cumplirse los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="5e9cc-115">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="5e9cc-116">El mapa se debe ordenar en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-116">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="5e9cc-117">No se debe reordenar el código MSIL instrumentado.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-117">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="5e9cc-118">El código MSIL original no se debe quitar.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-118">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="5e9cc-119">La asignación debe incluir entradas para asignar todos los puntos de secuencia del archivo de base de datos de programa (PDB).</span><span class="sxs-lookup"><span data-stu-id="5e9cc-119">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="5e9cc-120">La asignación no interpola las entradas que faltan.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-120">The map does not interpolate missing entries.</span></span> <span data-ttu-id="5e9cc-121">En el ejemplo siguiente se muestra una asignación y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-121">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="5e9cc-122">Conectarse</span><span class="sxs-lookup"><span data-stu-id="5e9cc-122">Map:</span></span>  
  
- <span data-ttu-id="5e9cc-123">0 desplazamiento anterior, 0 nuevo desplazamiento</span><span class="sxs-lookup"><span data-stu-id="5e9cc-123">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="5e9cc-124">5 desplazamiento anterior, 10 nuevo desplazamiento</span><span class="sxs-lookup"><span data-stu-id="5e9cc-124">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="5e9cc-125">9 desplazamiento anterior, 20 nuevo desplazamiento</span><span class="sxs-lookup"><span data-stu-id="5e9cc-125">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="5e9cc-126">Resultados:</span><span class="sxs-lookup"><span data-stu-id="5e9cc-126">Results:</span></span>  
  
- <span data-ttu-id="5e9cc-127">Un desplazamiento anterior de 0, 1, 2, 3 o 4 se asignará a un nuevo desplazamiento de 0.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-127">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="5e9cc-128">Un desplazamiento anterior de 5, 6, 7 u 8 se asignará al nuevo desplazamiento 10.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-128">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="5e9cc-129">Un desplazamiento anterior de 9 o superior se asignará al nuevo desplazamiento 20.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-129">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="5e9cc-130">Un nuevo desplazamiento de 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 se asignará al desplazamiento anterior 0.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-130">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="5e9cc-131">Un nuevo desplazamiento de 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 se asignará al anterior desplazamiento 5.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-131">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="5e9cc-132">Un nuevo desplazamiento de 20 o superior se asignará al anterior desplazamiento 9.</span><span class="sxs-lookup"><span data-stu-id="5e9cc-132">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e9cc-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e9cc-133">Requirements</span></span>  

 <span data-ttu-id="5e9cc-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e9cc-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e9cc-135">**Encabezado:** Cordebug. idl, Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="5e9cc-135">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="5e9cc-136">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e9cc-136">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e9cc-137">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e9cc-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e9cc-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e9cc-138">See also</span></span>

- [<span data-ttu-id="5e9cc-139">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="5e9cc-139">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="5e9cc-140">Depuración</span><span class="sxs-lookup"><span data-stu-id="5e9cc-140">Debugging</span></span>](index.md)
