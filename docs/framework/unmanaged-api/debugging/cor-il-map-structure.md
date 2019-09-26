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
ms.openlocfilehash: 5ae4c5743b01c4a9087323678d315473631cb32f
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274052"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="3aecb-102">COR_IL_MAP (Estructura)</span><span class="sxs-lookup"><span data-stu-id="3aecb-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="3aecb-103">Especifica los cambios en el desplazamiento relativo de una función.</span><span class="sxs-lookup"><span data-stu-id="3aecb-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aecb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3aecb-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="3aecb-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3aecb-105">Members</span></span>  
  
|<span data-ttu-id="3aecb-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3aecb-106">Member</span></span>|<span data-ttu-id="3aecb-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3aecb-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="3aecb-108">El desplazamiento anterior del lenguaje intermedio de Microsoft (MSIL) con respecto al principio de la función.</span><span class="sxs-lookup"><span data-stu-id="3aecb-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="3aecb-109">Nuevo desplazamiento de MSIL relativo al principio de la función.</span><span class="sxs-lookup"><span data-stu-id="3aecb-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="3aecb-110">`true`Si se sabe que la asignación es precisa; en caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="3aecb-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3aecb-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3aecb-111">Remarks</span></span>  
 <span data-ttu-id="3aecb-112">El formato del mapa es el siguiente: El depurador asumirá `oldOffset` que hace referencia a un desplazamiento de MSIL en el código MSIL original y sin modificar.</span><span class="sxs-lookup"><span data-stu-id="3aecb-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="3aecb-113">El `newOffset` parámetro hace referencia al desplazamiento de MSIL correspondiente en el nuevo código instrumentado.</span><span class="sxs-lookup"><span data-stu-id="3aecb-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="3aecb-114">Para que funcione correctamente, deben cumplirse los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="3aecb-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="3aecb-115">El mapa se debe ordenar en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="3aecb-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="3aecb-116">No se debe reordenar el código MSIL instrumentado.</span><span class="sxs-lookup"><span data-stu-id="3aecb-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="3aecb-117">El código MSIL original no se debe quitar.</span><span class="sxs-lookup"><span data-stu-id="3aecb-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="3aecb-118">La asignación debe incluir entradas para asignar todos los puntos de secuencia del archivo de base de datos de programa (PDB).</span><span class="sxs-lookup"><span data-stu-id="3aecb-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="3aecb-119">La asignación no interpola las entradas que faltan.</span><span class="sxs-lookup"><span data-stu-id="3aecb-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="3aecb-120">En el ejemplo siguiente se muestra una asignación y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="3aecb-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="3aecb-121">Conectarse</span><span class="sxs-lookup"><span data-stu-id="3aecb-121">Map:</span></span>  
  
- <span data-ttu-id="3aecb-122">0 desplazamiento anterior, 0 nuevo desplazamiento</span><span class="sxs-lookup"><span data-stu-id="3aecb-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="3aecb-123">5 desplazamiento anterior, 10 nuevo desplazamiento</span><span class="sxs-lookup"><span data-stu-id="3aecb-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="3aecb-124">9 desplazamiento anterior, 20 nuevo desplazamiento</span><span class="sxs-lookup"><span data-stu-id="3aecb-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="3aecb-125">Resultados</span><span class="sxs-lookup"><span data-stu-id="3aecb-125">Results:</span></span>  
  
- <span data-ttu-id="3aecb-126">Un desplazamiento anterior de 0, 1, 2, 3 o 4 se asignará a un nuevo desplazamiento de 0.</span><span class="sxs-lookup"><span data-stu-id="3aecb-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="3aecb-127">Un desplazamiento anterior de 5, 6, 7 u 8 se asignará al nuevo desplazamiento 10.</span><span class="sxs-lookup"><span data-stu-id="3aecb-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="3aecb-128">Un desplazamiento anterior de 9 o superior se asignará al nuevo desplazamiento 20.</span><span class="sxs-lookup"><span data-stu-id="3aecb-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="3aecb-129">Un nuevo desplazamiento de 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 se asignará al desplazamiento anterior 0.</span><span class="sxs-lookup"><span data-stu-id="3aecb-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="3aecb-130">Un nuevo desplazamiento de 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 se asignará al anterior desplazamiento 5.</span><span class="sxs-lookup"><span data-stu-id="3aecb-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="3aecb-131">Un nuevo desplazamiento de 20 o superior se asignará al anterior desplazamiento 9.</span><span class="sxs-lookup"><span data-stu-id="3aecb-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3aecb-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3aecb-132">Requirements</span></span>  
 <span data-ttu-id="3aecb-133">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3aecb-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3aecb-134">**Encabezado**: Cordebug. idl, Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="3aecb-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="3aecb-135">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3aecb-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3aecb-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3aecb-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aecb-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="3aecb-137">See also</span></span>

- [<span data-ttu-id="3aecb-138">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="3aecb-138">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="3aecb-139">Depuración</span><span class="sxs-lookup"><span data-stu-id="3aecb-139">Debugging</span></span>](index.md)
