---
title: "ICorDebugProcess5::EnumerateGCReferences (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateGCReferences
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44975a7896c71ce8061dedde13d31c4fbb88d6a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="e6b58-102">ICorDebugProcess5::EnumerateGCReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="e6b58-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="e6b58-103">Obtiene un enumerador para todos los objetos que se recolectarán como elementos no utilizados en un proceso.</span><span class="sxs-lookup"><span data-stu-id="e6b58-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6b58-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6b58-104">Syntax</span></span>  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6b58-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6b58-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="e6b58-106">[in] Un valor booleano que indica si las referencias débiles también se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="e6b58-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="e6b58-107">Si `enumerateWeakReferences` es `true`, el `ppEnum` enumerador incluye referencias fuertes y referencias débiles.</span><span class="sxs-lookup"><span data-stu-id="e6b58-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="e6b58-108">Si `enumerateWeakReferences` es `false`, el enumerador incluye solo las referencias fuertes.</span><span class="sxs-lookup"><span data-stu-id="e6b58-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="e6b58-109">[out] Un puntero a la dirección de un [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e6b58-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6b58-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6b58-110">Remarks</span></span>  
 <span data-ttu-id="e6b58-111">Este método proporciona una manera de determinar la cadena completa de raíz para cualquier objeto administrado en un proceso y puede usarse para determinar por qué un objeto mantiene la conexión.</span><span class="sxs-lookup"><span data-stu-id="e6b58-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6b58-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6b58-112">Requirements</span></span>  
 <span data-ttu-id="e6b58-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6b58-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6b58-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6b58-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6b58-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6b58-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6b58-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6b58-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6b58-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6b58-117">See Also</span></span>  
 [<span data-ttu-id="e6b58-118">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6b58-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="e6b58-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e6b58-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
