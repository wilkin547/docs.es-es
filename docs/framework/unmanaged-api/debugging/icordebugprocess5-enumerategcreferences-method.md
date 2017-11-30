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
ms.openlocfilehash: 4f517415412c93b009df81fc9a7f524449eb82a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="9bb16-102">ICorDebugProcess5::EnumerateGCReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="9bb16-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="9bb16-103">Obtiene un enumerador para todos los objetos que se recolectarán como elementos no utilizados en un proceso.</span><span class="sxs-lookup"><span data-stu-id="9bb16-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bb16-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9bb16-104">Syntax</span></span>  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9bb16-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9bb16-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="9bb16-106">[in] Un valor booleano que indica si las referencias débiles también se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="9bb16-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="9bb16-107">Si `enumerateWeakReferences` es `true`, el `ppEnum` enumerador incluye referencias fuertes y referencias débiles.</span><span class="sxs-lookup"><span data-stu-id="9bb16-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="9bb16-108">Si `enumerateWeakReferences` es `false`, el enumerador incluye solo las referencias fuertes.</span><span class="sxs-lookup"><span data-stu-id="9bb16-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="9bb16-109">[out] Un puntero a la dirección de un [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9bb16-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bb16-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9bb16-110">Remarks</span></span>  
 <span data-ttu-id="9bb16-111">Este método proporciona una manera de determinar la cadena completa de raíz para cualquier objeto administrado en un proceso y puede usarse para determinar por qué un objeto mantiene la conexión.</span><span class="sxs-lookup"><span data-stu-id="9bb16-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bb16-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9bb16-112">Requirements</span></span>  
 <span data-ttu-id="9bb16-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bb16-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bb16-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bb16-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bb16-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bb16-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bb16-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bb16-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bb16-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bb16-117">See Also</span></span>  
 [<span data-ttu-id="9bb16-118">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9bb16-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="9bb16-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9bb16-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
