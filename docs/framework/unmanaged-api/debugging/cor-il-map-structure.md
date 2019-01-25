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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7452b76509d5eca592cc3b95df1f77703ec1111
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561834"
---
# <a name="corilmap-structure"></a><span data-ttu-id="cfdac-102">COR_IL_MAP (Estructura)</span><span class="sxs-lookup"><span data-stu-id="cfdac-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="cfdac-103">Especifica los cambios en el desplazamiento relativo de una función.</span><span class="sxs-lookup"><span data-stu-id="cfdac-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfdac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfdac-104">Syntax</span></span>  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="cfdac-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="cfdac-105">Members</span></span>  
  
|<span data-ttu-id="cfdac-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="cfdac-106">Member</span></span>|<span data-ttu-id="cfdac-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfdac-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="cfdac-108">El antiguo lenguaje intermedio de Microsoft (MSIL) de desplazamiento en relación con el principio de la función.</span><span class="sxs-lookup"><span data-stu-id="cfdac-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="cfdac-109">Nuevo desplazamiento MSIL en relación con el principio de la función.</span><span class="sxs-lookup"><span data-stu-id="cfdac-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="cfdac-110">`true` Si se conoce la asignación para ser precisos; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="cfdac-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfdac-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cfdac-111">Remarks</span></span>  
 <span data-ttu-id="cfdac-112">El formato de la asignación es como sigue: El depurador supondrá que `oldOffset` hace referencia a un desplazamiento de MSIL dentro del código MSIL original, sin modificar.</span><span class="sxs-lookup"><span data-stu-id="cfdac-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="cfdac-113">El `newOffset` parámetro hace referencia al desplazamiento de MSIL correspondiente dentro del nuevo código instrumentado.</span><span class="sxs-lookup"><span data-stu-id="cfdac-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="cfdac-114">Para la ejecución paso a paso para que funcionen correctamente, deben cumplirse los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="cfdac-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
-   <span data-ttu-id="cfdac-115">El mapa se debe ordenar en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="cfdac-115">The map should be sorted in ascending order.</span></span>  
  
-   <span data-ttu-id="cfdac-116">No se debe reordenar código MSIL instrumentado.</span><span class="sxs-lookup"><span data-stu-id="cfdac-116">Instrumented MSIL code should not be reordered.</span></span>  
  
-   <span data-ttu-id="cfdac-117">No se debe quitar el código de MSIL original.</span><span class="sxs-lookup"><span data-stu-id="cfdac-117">Original MSIL code should not be removed.</span></span>  
  
-   <span data-ttu-id="cfdac-118">La asignación debería incluir las entradas para asignar todos los puntos de secuencia del archivo de programa (PDB) de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cfdac-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="cfdac-119">El mapa no interpola las entradas que faltan.</span><span class="sxs-lookup"><span data-stu-id="cfdac-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="cfdac-120">El ejemplo siguiente muestra un mapa y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="cfdac-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="cfdac-121">Mapa:</span><span class="sxs-lookup"><span data-stu-id="cfdac-121">Map:</span></span>  
  
-   <span data-ttu-id="cfdac-122">desplazamiento anterior 0, 0 nuevo desplazamiento</span><span class="sxs-lookup"><span data-stu-id="cfdac-122">0 old offset, 0 new offset</span></span>  
  
-   <span data-ttu-id="cfdac-123">desplazamiento anterior 5, 10 nuevo desplazamiento</span><span class="sxs-lookup"><span data-stu-id="cfdac-123">5 old offset, 10 new offset</span></span>  
  
-   <span data-ttu-id="cfdac-124">desplazamiento anterior 9, 20 nuevo desplazamiento</span><span class="sxs-lookup"><span data-stu-id="cfdac-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="cfdac-125">Resultados:</span><span class="sxs-lookup"><span data-stu-id="cfdac-125">Results:</span></span>  
  
-   <span data-ttu-id="cfdac-126">Un desplazamiento anterior de 0, 1, 2, 3 o 4 se asignará a un nuevo desplazamiento de 0.</span><span class="sxs-lookup"><span data-stu-id="cfdac-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
-   <span data-ttu-id="cfdac-127">Un desplazamiento anterior de 5, 6, 7 u 8 se asignará al nuevo desplazamiento de 10.</span><span class="sxs-lookup"><span data-stu-id="cfdac-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
-   <span data-ttu-id="cfdac-128">Un desplazamiento anterior de 9 o versiones posteriores se asignará al nuevo desplazamiento de 20.</span><span class="sxs-lookup"><span data-stu-id="cfdac-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
-   <span data-ttu-id="cfdac-129">Se asignará un nuevo desplazamiento de 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 al anterior desplazamiento de 0.</span><span class="sxs-lookup"><span data-stu-id="cfdac-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
-   <span data-ttu-id="cfdac-130">Un nuevo desplazamiento de 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 se asignará al anterior desplazamiento 5.</span><span class="sxs-lookup"><span data-stu-id="cfdac-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
-   <span data-ttu-id="cfdac-131">Se asignará un nuevo desplazamiento de 20 o superior al desplazamiento anterior de 9.</span><span class="sxs-lookup"><span data-stu-id="cfdac-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfdac-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cfdac-132">Requirements</span></span>  
 <span data-ttu-id="cfdac-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfdac-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfdac-134">**Encabezado**: CorDebug.idl, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="cfdac-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="cfdac-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfdac-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfdac-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfdac-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfdac-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfdac-137">See also</span></span>
- [<span data-ttu-id="cfdac-138">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="cfdac-138">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="cfdac-139">Depuración</span><span class="sxs-lookup"><span data-stu-id="cfdac-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
