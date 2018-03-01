---
title: "ICorDebugProcess5::EnumerateHandles (Método)"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c9bf9f1a4d565e0af4f3ee34a2805116407027d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="5c85a-102">ICorDebugProcess5::EnumerateHandles (Método)</span><span class="sxs-lookup"><span data-stu-id="5c85a-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="5c85a-103">Obtiene un enumerador para los identificadores de objeto en un proceso.</span><span class="sxs-lookup"><span data-stu-id="5c85a-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c85a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c85a-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c85a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c85a-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="5c85a-106">[in] Una combinación bit a bit de [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valores que especifica el tipo de identificadores que se incluirán en la colección.</span><span class="sxs-lookup"><span data-stu-id="5c85a-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="5c85a-107">[out] Un puntero a la dirección de un [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5c85a-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c85a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c85a-108">Remarks</span></span>  
 <span data-ttu-id="5c85a-109">`EnumerateHandles`es una función auxiliar que admite la inspección de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="5c85a-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="5c85a-110">Es similar a la [icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) método, salvo que, en lugar de rellenar un [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) colección con todos los objetos que se recolectarán como elementos no utilizados, lo incluye solo los objetos que tienen identificadores de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="5c85a-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="5c85a-111">El `types` parámetro especifica los tipos de identificador que se incluirán en la colección.</span><span class="sxs-lookup"><span data-stu-id="5c85a-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="5c85a-112">`types`puede ser cualquiera de los siguientes tres miembros de la [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeración:</span><span class="sxs-lookup"><span data-stu-id="5c85a-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
-   <span data-ttu-id="5c85a-113">`CorHandleStrongOnly`(controladores para solo referencias fuertes).</span><span class="sxs-lookup"><span data-stu-id="5c85a-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
-   <span data-ttu-id="5c85a-114">`CorHandleWeakOnly`(controladores para solo referencias débiles).</span><span class="sxs-lookup"><span data-stu-id="5c85a-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
-   <span data-ttu-id="5c85a-115">`CorHandleAll`(todos los controladores).</span><span class="sxs-lookup"><span data-stu-id="5c85a-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c85a-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c85a-116">Requirements</span></span>  
 <span data-ttu-id="5c85a-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c85a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c85a-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c85a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c85a-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c85a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c85a-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c85a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c85a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c85a-121">See Also</span></span>  
 [<span data-ttu-id="5c85a-122">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="5c85a-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="5c85a-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="5c85a-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
