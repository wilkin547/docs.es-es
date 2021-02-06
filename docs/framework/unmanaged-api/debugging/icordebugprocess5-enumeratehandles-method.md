---
description: 'Más información sobre: ICorDebugProcess5:: Enumeratehandles ((método)'
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
ms.openlocfilehash: 62ca1390ceec634e6651dc013345688fe5892bcd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649915"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="b7b4f-103">ICorDebugProcess5::EnumerateHandles (Método)</span><span class="sxs-lookup"><span data-stu-id="b7b4f-103">ICorDebugProcess5::EnumerateHandles Method</span></span>

<span data-ttu-id="b7b4f-104">Obtiene un enumerador para los identificadores de objetos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="b7b4f-104">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7b4f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7b4f-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7b4f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7b4f-106">Parameters</span></span>  

 `types`  
 <span data-ttu-id="b7b4f-107">de Combinación bit a bit de valores de [corgcreferencetype (](corgcreferencetype-enumeration.md) que especifica el tipo de identificadores que se van a incluir en la colección.</span><span class="sxs-lookup"><span data-stu-id="b7b4f-107">[in] A bitwise combination of [CorGCReferenceType](corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="b7b4f-108">enuncia Puntero a la dirección de un [icordebuggcreferenceenum (](icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos que se van a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="b7b4f-108">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7b4f-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b7b4f-109">Remarks</span></span>  

 <span data-ttu-id="b7b4f-110">`EnumerateHandles` es una función auxiliar que admite la inspección de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="b7b4f-110">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="b7b4f-111">Es similar al método [ICorDebugProcess5:: enumerategcreferences (](icordebugprocess5-enumerategcreferences-method.md) , salvo que, en lugar de rellenar una colección [icordebuggcreferenceenum (](icordebuggcreferenceenum-interface.md) con todos los objetos que se van a recopilar de elementos no utilizados, solo incluye los objetos que tienen identificadores de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="b7b4f-111">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="b7b4f-112">El `types` parámetro especifica los tipos de identificadores que se van a incluir en la colección.</span><span class="sxs-lookup"><span data-stu-id="b7b4f-112">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="b7b4f-113">`types` puede ser cualquiera de los siguientes tres miembros de la enumeración [corgcreferencetype (](corgcreferencetype-enumeration.md) :</span><span class="sxs-lookup"><span data-stu-id="b7b4f-113">`types` can be any of the following three members of the [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="b7b4f-114">`CorHandleStrongOnly` (solo controla las referencias fuertes).</span><span class="sxs-lookup"><span data-stu-id="b7b4f-114">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="b7b4f-115">`CorHandleWeakOnly` (solo controla las referencias débiles).</span><span class="sxs-lookup"><span data-stu-id="b7b4f-115">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="b7b4f-116">`CorHandleAll` (todos los identificadores).</span><span class="sxs-lookup"><span data-stu-id="b7b4f-116">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7b4f-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7b4f-117">Requirements</span></span>  

 <span data-ttu-id="b7b4f-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7b4f-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7b4f-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7b4f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7b4f-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7b4f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7b4f-121">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7b4f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b4f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7b4f-122">See also</span></span>

- [<span data-ttu-id="b7b4f-123">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="b7b4f-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="b7b4f-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="b7b4f-124">Debugging</span></span>](index.md)
