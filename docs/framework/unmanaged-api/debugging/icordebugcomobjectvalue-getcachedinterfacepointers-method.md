---
title: "ICorDebugComObjectValue::GetCachedInterfacePointers (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugComObjectValue::GetCachedInterfacePointers
api_location: mscordbi.dll
f1_keywords: ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 607300d6b46f3ee20545c50872b99df483b1614c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="26e4d-102">ICorDebugComObjectValue::GetCachedInterfacePointers (Método)</span><span class="sxs-lookup"><span data-stu-id="26e4d-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="26e4d-103">Obtiene los punteros de interfaz sin formato que se almacena en caché en el contenedor invocable en tiempo de ejecución actual (RCW).</span><span class="sxs-lookup"><span data-stu-id="26e4d-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26e4d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26e4d-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26e4d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="26e4d-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="26e4d-106">[in] Un valor que indica si el método devolverá solo [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) o todas las interfaces COM que se almacenan en caché por el contenedor invocable en tiempo de ejecución (RCW).</span><span class="sxs-lookup"><span data-stu-id="26e4d-106">[in] A value that indicates whether the method will return only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="26e4d-107">[in] El número de objetos cuyas direcciones se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="26e4d-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="26e4d-108">[out] Un puntero al número de `CORDB_ADDRESS` valores realmente devueltos en `ptrs`.</span><span class="sxs-lookup"><span data-stu-id="26e4d-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="26e4d-109">Un puntero a la dirección inicial de una matriz de `CORDB_ADDRESS` valores que contienen las direcciones de los objetos de interfaz en caché.</span><span class="sxs-lookup"><span data-stu-id="26e4d-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26e4d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26e4d-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26e4d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26e4d-111">Requirements</span></span>  
 <span data-ttu-id="26e4d-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26e4d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26e4d-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26e4d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26e4d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26e4d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26e4d-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26e4d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e4d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="26e4d-116">See Also</span></span>  
 [<span data-ttu-id="26e4d-117">ICorDebugComObjectValue (interfaz)</span><span class="sxs-lookup"><span data-stu-id="26e4d-117">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 [<span data-ttu-id="26e4d-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="26e4d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
