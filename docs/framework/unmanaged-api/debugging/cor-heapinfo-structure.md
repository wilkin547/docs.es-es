---
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
ms.openlocfilehash: b6fd3682290c9752125aed7b9663c6704ade25de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132332"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="3a2d4-102">COR_HEAPINFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="3a2d4-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="3a2d4-103">Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es enumerable.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a2d4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a2d4-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="3a2d4-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3a2d4-105">Members</span></span>  
  
|<span data-ttu-id="3a2d4-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3a2d4-106">Member</span></span>|<span data-ttu-id="3a2d4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a2d4-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="3a2d4-108">`true` si las estructuras de recolección de elementos no utilizados son válidas y se puede enumerar el montón; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="3a2d4-109">Tamaño, en bytes, de los punteros en la arquitectura de destino.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="3a2d4-110">El número de montones de recolección de elementos no utilizados lógicas en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="3a2d4-111">`TRUE` si la recolección de elementos no utilizados simultánea (en segundo plano) está habilitada; de lo contrario, `FALSE`.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="3a2d4-112">Miembro de la enumeración [cordebuggctype (](cordebuggctype-enumeration.md) que indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a2d4-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a2d4-113">Remarks</span></span>  
 <span data-ttu-id="3a2d4-114">Se devuelve una instancia de la estructura `COR_HEAPINFO` llamando al método [ICorDebugProcess5:: getgcheapinformation (](icordebugprocess5-getgcheapinformation-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3a2d4-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="3a2d4-115">Antes de enumerar los objetos en el montón de recolección de elementos no utilizados, debe comprobar siempre el campo `areGCStructuresValid` para asegurarse de que el montón se encuentra en un estado Enumerable.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="3a2d4-116">Para obtener más información, vea el método [ICorDebugProcess5:: getgcheapinformation (](icordebugprocess5-getgcheapinformation-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3a2d4-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a2d4-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a2d4-117">Requirements</span></span>  
 <span data-ttu-id="3a2d4-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a2d4-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a2d4-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a2d4-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a2d4-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a2d4-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a2d4-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a2d4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a2d4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a2d4-122">See also</span></span>

- [<span data-ttu-id="3a2d4-123">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="3a2d4-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="3a2d4-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="3a2d4-124">Debugging</span></span>](index.md)
