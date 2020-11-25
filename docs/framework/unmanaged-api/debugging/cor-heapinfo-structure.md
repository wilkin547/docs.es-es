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
ms.openlocfilehash: 5400350e1c489ec4c2ff3cddf83a4f1a8a0c7947
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726605"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="2545f-102">COR_HEAPINFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="2545f-102">COR_HEAPINFO Structure</span></span>

<span data-ttu-id="2545f-103">Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es enumerable.</span><span class="sxs-lookup"><span data-stu-id="2545f-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2545f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2545f-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="2545f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2545f-105">Members</span></span>  
  
|<span data-ttu-id="2545f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="2545f-106">Member</span></span>|<span data-ttu-id="2545f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2545f-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="2545f-108">`true` Si las estructuras de recolección de elementos no utilizados son válidas y se puede enumerar el montón; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="2545f-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="2545f-109">Tamaño, en bytes, de los punteros en la arquitectura de destino.</span><span class="sxs-lookup"><span data-stu-id="2545f-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="2545f-110">El número de montones de recolección de elementos no utilizados lógicas en el proceso.</span><span class="sxs-lookup"><span data-stu-id="2545f-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="2545f-111">`TRUE` Si la recolección de elementos no utilizados simultánea (en segundo plano) está habilitada; en caso contrario, `FALSE` .</span><span class="sxs-lookup"><span data-stu-id="2545f-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="2545f-112">Miembro de la enumeración [cordebuggctype (](cordebuggctype-enumeration.md) que indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.</span><span class="sxs-lookup"><span data-stu-id="2545f-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2545f-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2545f-113">Remarks</span></span>  

 <span data-ttu-id="2545f-114">Se devuelve una instancia de la `COR_HEAPINFO` estructura llamando al método [ICorDebugProcess5:: getgcheapinformation (](icordebugprocess5-getgcheapinformation-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2545f-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="2545f-115">Antes de enumerar los objetos en el montón de recolección de elementos no utilizados, debe comprobar siempre el `areGCStructuresValid` campo para asegurarse de que el montón se encuentra en un estado Enumerable.</span><span class="sxs-lookup"><span data-stu-id="2545f-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="2545f-116">Para obtener más información, vea el método [ICorDebugProcess5:: getgcheapinformation (](icordebugprocess5-getgcheapinformation-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2545f-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2545f-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2545f-117">Requirements</span></span>  

 <span data-ttu-id="2545f-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2545f-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2545f-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2545f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2545f-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2545f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2545f-121">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2545f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2545f-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2545f-122">See also</span></span>

- [<span data-ttu-id="2545f-123">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="2545f-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="2545f-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="2545f-124">Debugging</span></span>](index.md)
