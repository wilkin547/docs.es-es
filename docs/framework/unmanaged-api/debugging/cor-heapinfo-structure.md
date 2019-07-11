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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dd233643bd18b60b7d6176c34ee57e4061daf7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740656"
---
# <a name="corheapinfo-structure"></a><span data-ttu-id="4b5cd-102">COR_HEAPINFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="4b5cd-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="4b5cd-103">Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es enumerable.</span><span class="sxs-lookup"><span data-stu-id="4b5cd-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b5cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b5cd-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="4b5cd-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4b5cd-105">Members</span></span>  
  
|<span data-ttu-id="4b5cd-106">Member</span><span class="sxs-lookup"><span data-stu-id="4b5cd-106">Member</span></span>|<span data-ttu-id="4b5cd-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4b5cd-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="4b5cd-108">`true` Si las estructuras de la colección de elementos no utilizados son válidas y se puede enumerar el montón; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="4b5cd-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="4b5cd-109">El tamaño, en bytes, de punteros en la arquitectura de destino.</span><span class="sxs-lookup"><span data-stu-id="4b5cd-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="4b5cd-110">El número de recolección de elementos lógicos montones en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4b5cd-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="4b5cd-111">`TRUE` Si simultánea está habilitada la recolección de elementos (fondo); en caso contrario, `FALSE`.</span><span class="sxs-lookup"><span data-stu-id="4b5cd-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="4b5cd-112">Un miembro de la [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) enumeración que indica si el recolector de elementos no utilizados se ejecuta en una estación de trabajo o un servidor.</span><span class="sxs-lookup"><span data-stu-id="4b5cd-112">A member of the [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b5cd-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4b5cd-113">Remarks</span></span>  
 <span data-ttu-id="4b5cd-114">Una instancia de la `COR_HEAPINFO` estructura se devuelve mediante una llamada a la [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4b5cd-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="4b5cd-115">Antes de enumerar los objetos del montón de la colección de elementos no utilizados, debe comprobar siempre el `areGCStructuresValid` campo para asegurarse de que el montón está en un estado enumerable.</span><span class="sxs-lookup"><span data-stu-id="4b5cd-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="4b5cd-116">Para obtener más información, consulte el [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4b5cd-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b5cd-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b5cd-117">Requirements</span></span>  
 <span data-ttu-id="4b5cd-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b5cd-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b5cd-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b5cd-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b5cd-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b5cd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b5cd-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b5cd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b5cd-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b5cd-122">See also</span></span>

- [<span data-ttu-id="4b5cd-123">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="4b5cd-123">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="4b5cd-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="4b5cd-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
