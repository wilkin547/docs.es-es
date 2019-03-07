---
title: ICorDebugProcess5::EnumerateGCReferences (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54e2648765d896c189cc2deb5590a0a2a9b3f410
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476493"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="b5148-102">ICorDebugProcess5::EnumerateGCReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="b5148-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="b5148-103">Obtiene un enumerador para todos los objetos que se van a recopilar los elementos no utilizados en un proceso.</span><span class="sxs-lookup"><span data-stu-id="b5148-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5148-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5148-104">Syntax</span></span>  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5148-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b5148-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="b5148-106">[in] Un valor booleano que indica si las referencias débiles son también van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="b5148-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="b5148-107">Si `enumerateWeakReferences` es `true`, el `ppEnum` enumerador incluye referencias fuertes y las referencias débiles.</span><span class="sxs-lookup"><span data-stu-id="b5148-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="b5148-108">Si `enumerateWeakReferences` es `false`, el enumerador incluye solo las referencias fuertes.</span><span class="sxs-lookup"><span data-stu-id="b5148-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="b5148-109">[out] Un puntero a la dirección de un [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos de recopilar los elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b5148-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5148-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5148-110">Remarks</span></span>  
 <span data-ttu-id="b5148-111">Este método proporciona una manera de determinar la cadena completa de raíz para cualquier objeto administrado en un proceso y se puede usar para determinar por qué un objeto todavía está activo.</span><span class="sxs-lookup"><span data-stu-id="b5148-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5148-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5148-112">Requirements</span></span>  
 <span data-ttu-id="b5148-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5148-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5148-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5148-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5148-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5148-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5148-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5148-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5148-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5148-117">See also</span></span>
- [<span data-ttu-id="b5148-118">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b5148-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="b5148-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b5148-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
