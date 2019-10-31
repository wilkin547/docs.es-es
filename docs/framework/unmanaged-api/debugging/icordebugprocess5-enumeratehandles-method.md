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
ms.openlocfilehash: e0e68dba1f4d9ac5fa618aa842b823dcc046e70e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129674"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="b82cf-102">ICorDebugProcess5::EnumerateHandles (Método)</span><span class="sxs-lookup"><span data-stu-id="b82cf-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="b82cf-103">Obtiene un enumerador para los identificadores de objetos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="b82cf-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b82cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b82cf-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b82cf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b82cf-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="b82cf-106">de Combinación bit a bit de valores de [corgcreferencetype (](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) que especifica el tipo de identificadores que se van a incluir en la colección.</span><span class="sxs-lookup"><span data-stu-id="b82cf-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="b82cf-107">enuncia Puntero a la dirección de un [icordebuggcreferenceenum (](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos que se van a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="b82cf-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b82cf-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b82cf-108">Remarks</span></span>  
 <span data-ttu-id="b82cf-109">`EnumerateHandles` es una función auxiliar que admite la inspección de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="b82cf-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="b82cf-110">Es similar al método [ICorDebugProcess5:: enumerategcreferences (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) , salvo que, en lugar de rellenar una colección [icordebuggcreferenceenum (](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) con todos los objetos que se van a recopilar de elementos no utilizados, solo incluye los objetos que tienen identificadores de tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="b82cf-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="b82cf-111">El parámetro `types` especifica los tipos de identificadores que se van a incluir en la colección.</span><span class="sxs-lookup"><span data-stu-id="b82cf-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="b82cf-112">`types` puede ser cualquiera de los siguientes tres miembros de la enumeración [corgcreferencetype (](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) :</span><span class="sxs-lookup"><span data-stu-id="b82cf-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="b82cf-113">`CorHandleStrongOnly` (solo controla las referencias fuertes).</span><span class="sxs-lookup"><span data-stu-id="b82cf-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="b82cf-114">`CorHandleWeakOnly` (solo identificadores de referencias débiles).</span><span class="sxs-lookup"><span data-stu-id="b82cf-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="b82cf-115">`CorHandleAll` (todos los identificadores).</span><span class="sxs-lookup"><span data-stu-id="b82cf-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b82cf-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b82cf-116">Requirements</span></span>  
 <span data-ttu-id="b82cf-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b82cf-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b82cf-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b82cf-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b82cf-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b82cf-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b82cf-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b82cf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b82cf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b82cf-121">See also</span></span>

- [<span data-ttu-id="b82cf-122">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="b82cf-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="b82cf-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="b82cf-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
