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
ms.openlocfilehash: 37659262695b63a6dd6390c62c4bb7e04fdadca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179308"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="b41e4-102">COR_HEAPINFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="b41e4-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="b41e4-103">Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es enumerable.</span><span class="sxs-lookup"><span data-stu-id="b41e4-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b41e4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b41e4-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="b41e4-105">Members</span><span class="sxs-lookup"><span data-stu-id="b41e4-105">Members</span></span>  
  
|<span data-ttu-id="b41e4-106">Member</span><span class="sxs-lookup"><span data-stu-id="b41e4-106">Member</span></span>|<span data-ttu-id="b41e4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b41e4-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="b41e4-108">`true`si las estructuras de recolección de elementos no utilizados son válidas y se puede enumerar el montón; de `false`lo contrario, .</span><span class="sxs-lookup"><span data-stu-id="b41e4-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="b41e4-109">El tamaño, en bytes, de los punteros en la arquitectura de destino.</span><span class="sxs-lookup"><span data-stu-id="b41e4-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="b41e4-110">El número de montones lógicos de recolección de elementos no utilizados en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b41e4-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="b41e4-111">`TRUE`si la recolección simultánea (de fondo) de elementos no utilizados está habilitada; de `FALSE`lo contrario, .</span><span class="sxs-lookup"><span data-stu-id="b41e4-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="b41e4-112">Miembro de la [enumeración CorDebugGCType](cordebuggctype-enumeration.md) que indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.</span><span class="sxs-lookup"><span data-stu-id="b41e4-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b41e4-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b41e4-113">Remarks</span></span>  
 <span data-ttu-id="b41e4-114">Se devuelve `COR_HEAPINFO` una instancia de la estructura mediante una llamada a la [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b41e4-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="b41e4-115">Antes de enumerar objetos en el montón `areGCStructuresValid` de recolección de elementos no utilizados, siempre debe comprobar el campo para asegurarse de que el montón está en un estado enumerable.</span><span class="sxs-lookup"><span data-stu-id="b41e4-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="b41e4-116">Para obtener más información, vea el [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b41e4-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b41e4-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b41e4-117">Requirements</span></span>  
 <span data-ttu-id="b41e4-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b41e4-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b41e4-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b41e4-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b41e4-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b41e4-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b41e4-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b41e4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b41e4-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b41e4-122">See also</span></span>

- [<span data-ttu-id="b41e4-123">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="b41e4-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="b41e4-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="b41e4-124">Debugging</span></span>](index.md)
