---
description: 'Más información acerca de: estructura de COR_HEAPINFO'
title: COR_HEAPINFO (Estructura)
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
ms.openlocfilehash: 0841739172b3eaf807813af28e0b20fbb54608b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712320"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="bb616-103">COR_HEAPINFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="bb616-103">COR_HEAPINFO Structure</span></span>

<span data-ttu-id="bb616-104">Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es enumerable.</span><span class="sxs-lookup"><span data-stu-id="bb616-104">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb616-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb616-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="bb616-106">Members</span><span class="sxs-lookup"><span data-stu-id="bb616-106">Members</span></span>  
  
|<span data-ttu-id="bb616-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="bb616-107">Member</span></span>|<span data-ttu-id="bb616-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb616-108">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="bb616-109">`true` Si las estructuras de recolección de elementos no utilizados son válidas y se puede enumerar el montón; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="bb616-109">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="bb616-110">Tamaño, en bytes, de los punteros en la arquitectura de destino.</span><span class="sxs-lookup"><span data-stu-id="bb616-110">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="bb616-111">El número de montones de recolección de elementos no utilizados lógicas en el proceso.</span><span class="sxs-lookup"><span data-stu-id="bb616-111">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="bb616-112">`TRUE` Si la recolección de elementos no utilizados simultánea (en segundo plano) está habilitada; en caso contrario, `FALSE` .</span><span class="sxs-lookup"><span data-stu-id="bb616-112">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="bb616-113">Miembro de la enumeración [cordebuggctype (](cordebuggctype-enumeration.md) que indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.</span><span class="sxs-lookup"><span data-stu-id="bb616-113">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb616-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bb616-114">Remarks</span></span>  

 <span data-ttu-id="bb616-115">Se devuelve una instancia de la `COR_HEAPINFO` estructura llamando al método [ICorDebugProcess5:: getgcheapinformation (](icordebugprocess5-getgcheapinformation-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bb616-115">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="bb616-116">Antes de enumerar los objetos en el montón de recolección de elementos no utilizados, debe comprobar siempre el `areGCStructuresValid` campo para asegurarse de que el montón se encuentra en un estado Enumerable.</span><span class="sxs-lookup"><span data-stu-id="bb616-116">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="bb616-117">Para obtener más información, vea el método [ICorDebugProcess5:: getgcheapinformation (](icordebugprocess5-getgcheapinformation-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bb616-117">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb616-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb616-118">Requirements</span></span>  

 <span data-ttu-id="bb616-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb616-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb616-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb616-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb616-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb616-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb616-122">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb616-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb616-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb616-123">See also</span></span>

- [<span data-ttu-id="bb616-124">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="bb616-124">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="bb616-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="bb616-125">Debugging</span></span>](index.md)
