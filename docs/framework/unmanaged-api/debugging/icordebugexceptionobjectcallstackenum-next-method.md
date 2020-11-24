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
ms.openlocfilehash: 17d5367564ec1ec98efc264ad9a5794c0d04a947
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672141"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="85c68-102">ICorDebugExceptionObjectCallStackEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="85c68-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>

<span data-ttu-id="85c68-103">Obtiene el número especificado de instancias de [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) que contienen información de la pila de llamadas de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="85c68-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c68-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85c68-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85c68-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85c68-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="85c68-106">de El número de instancias de [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="85c68-106">[in] The number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="85c68-107">enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="85c68-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="85c68-108">enuncia Un puntero al número de instancias de [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="85c68-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85c68-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="85c68-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85c68-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85c68-110">Requirements</span></span>  

 <span data-ttu-id="85c68-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85c68-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85c68-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85c68-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85c68-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85c68-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85c68-114">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85c68-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c68-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85c68-115">See also</span></span>

- [<span data-ttu-id="85c68-116">ICorDebugExceptionObjectCallStackEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85c68-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="85c68-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="85c68-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
