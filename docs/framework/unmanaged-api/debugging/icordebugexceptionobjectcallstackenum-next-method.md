---
title: ICorDebugExceptionObjectCallStackEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c33f76b5eaa87c0b69497547732564921f662d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099474"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="3a39c-102">ICorDebugExceptionObjectCallStackEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="3a39c-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>
<span data-ttu-id="3a39c-103">Obtiene el número especificado de [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instancias que contienen información de la pila de llamadas de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="3a39c-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a39c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a39c-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a39c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a39c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3a39c-106">[in] El número de [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="3a39c-106">[in] The number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="3a39c-107">[out] Una matriz de punteros, cada uno de los cuales señala a un [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="3a39c-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="3a39c-108">[out] Un puntero al número de [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="3a39c-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a39c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a39c-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a39c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a39c-110">Requirements</span></span>  
 <span data-ttu-id="3a39c-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a39c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a39c-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a39c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a39c-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a39c-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3a39c-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3a39c-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3a39c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a39c-115">See also</span></span>

- [<span data-ttu-id="3a39c-116">ICorDebugExceptionObjectCallStackEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a39c-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="3a39c-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3a39c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
