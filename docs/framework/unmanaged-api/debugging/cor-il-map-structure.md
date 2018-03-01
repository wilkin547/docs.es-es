---
title: COR_IL_MAP (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e2772833d75ced2209896ca37cf6cf37fb965f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corilmap-structure"></a><span data-ttu-id="a5f97-102">COR_IL_MAP (Estructura)</span><span class="sxs-lookup"><span data-stu-id="a5f97-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="a5f97-103">Especifica los cambios en el desplazamiento relativo de una función.</span><span class="sxs-lookup"><span data-stu-id="a5f97-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5f97-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5f97-104">Syntax</span></span>  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="a5f97-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a5f97-105">Members</span></span>  
  
|<span data-ttu-id="a5f97-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a5f97-106">Member</span></span>|<span data-ttu-id="a5f97-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5f97-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="a5f97-108">El antiguo lenguaje intermedio de Microsoft (MSIL) desplaza en relación con el principio de la función.</span><span class="sxs-lookup"><span data-stu-id="a5f97-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="a5f97-109">El desplazamiento MSIL nueva relativa al comienzo de la función.</span><span class="sxs-lookup"><span data-stu-id="a5f97-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="a5f97-110">`true`Si la asignación se sabe que es preciso; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a5f97-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5f97-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5f97-111">Remarks</span></span>  
 <span data-ttu-id="a5f97-112">El formato de la asignación es como sigue: el depurador supondrá que `oldOffset` hace referencia a un desplazamiento MSIL dentro del código MSIL original, sin modificar.</span><span class="sxs-lookup"><span data-stu-id="a5f97-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="a5f97-113">El `newOffset` parámetro hace referencia al desplazamiento correspondiente de MSIL dentro del nuevo código instrumentado.</span><span class="sxs-lookup"><span data-stu-id="a5f97-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="a5f97-114">Para la ejecución paso a paso para que funcione correctamente, deben cumplirse los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="a5f97-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
-   <span data-ttu-id="a5f97-115">La asignación se debe ordenar en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="a5f97-115">The map should be sorted in ascending order.</span></span>  
  
-   <span data-ttu-id="a5f97-116">No se debe reordenar el código MSIL instrumentado.</span><span class="sxs-lookup"><span data-stu-id="a5f97-116">Instrumented MSIL code should not be reordered.</span></span>  
  
-   <span data-ttu-id="a5f97-117">Código de MSIL original no se debe quitar.</span><span class="sxs-lookup"><span data-stu-id="a5f97-117">Original MSIL code should not be removed.</span></span>  
  
-   <span data-ttu-id="a5f97-118">La asignación debería incluir las entradas para asignar todos los puntos de secuencia del archivo de programa (PDB) de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a5f97-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="a5f97-119">El mapa no interpola las entradas que faltan.</span><span class="sxs-lookup"><span data-stu-id="a5f97-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="a5f97-120">En el ejemplo siguiente se muestra un mapa y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="a5f97-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="a5f97-121">Asignar:</span><span class="sxs-lookup"><span data-stu-id="a5f97-121">Map:</span></span>  
  
-   <span data-ttu-id="a5f97-122">0 desplazamiento anterior, 0 nuevo desplazamiento</span><span class="sxs-lookup"><span data-stu-id="a5f97-122">0 old offset, 0 new offset</span></span>  
  
-   <span data-ttu-id="a5f97-123">desplazamiento anterior 5, 10 desvío nueva</span><span class="sxs-lookup"><span data-stu-id="a5f97-123">5 old offset, 10 new offset</span></span>  
  
-   <span data-ttu-id="a5f97-124">desplazamiento anterior 9, 20 nuevo desplazamiento</span><span class="sxs-lookup"><span data-stu-id="a5f97-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="a5f97-125">Resultados:</span><span class="sxs-lookup"><span data-stu-id="a5f97-125">Results:</span></span>  
  
-   <span data-ttu-id="a5f97-126">Un desplazamiento anterior de 0, 1, 2, 3 o 4 se asignarán a un nuevo desplazamiento de 0.</span><span class="sxs-lookup"><span data-stu-id="a5f97-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
-   <span data-ttu-id="a5f97-127">Un desplazamiento anterior de 5, 6, 7 u 8 se asignarán al nuevo desplazamiento de 10.</span><span class="sxs-lookup"><span data-stu-id="a5f97-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
-   <span data-ttu-id="a5f97-128">Un desplazamiento anterior de 9 o versiones posteriores se asignarán al nuevo desplazamiento de 20.</span><span class="sxs-lookup"><span data-stu-id="a5f97-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
-   <span data-ttu-id="a5f97-129">Se asignará un nuevo desplazamiento de 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 al anterior desplazamiento de 0.</span><span class="sxs-lookup"><span data-stu-id="a5f97-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
-   <span data-ttu-id="a5f97-130">Un desplazamiento de 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 nuevos se asignarán al anterior desplazamiento de 5.</span><span class="sxs-lookup"><span data-stu-id="a5f97-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
-   <span data-ttu-id="a5f97-131">Se asignará un nuevo desplazamiento de 20 o superior al anterior desplazamiento de 9.</span><span class="sxs-lookup"><span data-stu-id="a5f97-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5f97-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5f97-132">Requirements</span></span>  
 <span data-ttu-id="a5f97-133">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5f97-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5f97-134">**Encabezado:** CorDebug.idl, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="a5f97-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="a5f97-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5f97-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5f97-136">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5f97-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5f97-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5f97-137">See Also</span></span>  
 [<span data-ttu-id="a5f97-138">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="a5f97-138">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="a5f97-139">Depuración</span><span class="sxs-lookup"><span data-stu-id="a5f97-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
