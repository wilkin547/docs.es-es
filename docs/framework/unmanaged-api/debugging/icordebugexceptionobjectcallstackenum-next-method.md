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
ms.openlocfilehash: 6c742f541b358b40e6e2fd44ca437b0dd72e29b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091084"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="bc0f3-102">ICorDebugExceptionObjectCallStackEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="bc0f3-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>
<span data-ttu-id="bc0f3-103">Obtiene el número especificado de instancias de [cordebugexceptionobjectstackframe (](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) que contienen información de la pila de llamadas de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="bc0f3-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc0f3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc0f3-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc0f3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc0f3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="bc0f3-106">de El número de instancias de [cordebugexceptionobjectstackframe (](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="bc0f3-106">[in] The number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="bc0f3-107">enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [cordebugexceptionobjectstackframe (](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="bc0f3-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="bc0f3-108">enuncia Un puntero al número de instancias de [cordebugexceptionobjectstackframe (](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="bc0f3-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc0f3-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bc0f3-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc0f3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc0f3-110">Requirements</span></span>  
 <span data-ttu-id="bc0f3-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc0f3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc0f3-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc0f3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc0f3-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc0f3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc0f3-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc0f3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc0f3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc0f3-115">See also</span></span>

- [<span data-ttu-id="bc0f3-116">ICorDebugExceptionObjectCallStackEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc0f3-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="bc0f3-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bc0f3-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
