---
title: ICorDebugProcess5::EnumerateHandles (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f2177702c6c5999033d0852a932e52c0725fb8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422664"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="c8f2f-102">ICorDebugProcess5::EnumerateHandles (Método)</span><span class="sxs-lookup"><span data-stu-id="c8f2f-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="c8f2f-103">Obtiene un enumerador para los identificadores de objeto en un proceso.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8f2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8f2f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8f2f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c8f2f-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="c8f2f-106">[in] Una combinación bit a bit de [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valores que especifica el tipo de identificadores que se incluirán en la colección.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="c8f2f-107">[out] Un puntero a la dirección de un [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8f2f-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c8f2f-108">Remarks</span></span>  
 <span data-ttu-id="c8f2f-109">`EnumerateHandles` es una función auxiliar que admite la inspección de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="c8f2f-110">Es similar a la [icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) método, salvo que, en lugar de rellenar un [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) colección con todos los objetos que se recolectarán como elementos no utilizados, lo incluye solo los objetos que tienen identificadores de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="c8f2f-111">El `types` parámetro especifica los tipos de identificador que se incluirán en la colección.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="c8f2f-112">`types` puede ser cualquiera de los siguientes tres miembros de la [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeración:</span><span class="sxs-lookup"><span data-stu-id="c8f2f-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
-   <span data-ttu-id="c8f2f-113">`CorHandleStrongOnly` (controladores para solo referencias fuertes).</span><span class="sxs-lookup"><span data-stu-id="c8f2f-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
-   <span data-ttu-id="c8f2f-114">`CorHandleWeakOnly` (controladores para solo referencias débiles).</span><span class="sxs-lookup"><span data-stu-id="c8f2f-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
-   <span data-ttu-id="c8f2f-115">`CorHandleAll` (todos los controladores).</span><span class="sxs-lookup"><span data-stu-id="c8f2f-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8f2f-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8f2f-116">Requirements</span></span>  
 <span data-ttu-id="c8f2f-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8f2f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8f2f-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8f2f-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8f2f-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8f2f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8f2f-120">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8f2f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f2f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8f2f-121">See Also</span></span>  
 [<span data-ttu-id="c8f2f-122">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="c8f2f-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="c8f2f-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="c8f2f-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
