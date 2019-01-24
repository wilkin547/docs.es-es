---
title: ICorDebugStackWalk::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eee75bc16f46ba5ea58fc42c570e48b09ab9a2e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553235"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="7b38b-102">ICorDebugStackWalk::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="7b38b-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="7b38b-103">Mueve el [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) objeto al marco siguiente.</span><span class="sxs-lookup"><span data-stu-id="7b38b-103">Moves the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b38b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b38b-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7b38b-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7b38b-105">Return Value</span></span>  
 <span data-ttu-id="7b38b-106">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="7b38b-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7b38b-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7b38b-107">HRESULT</span></span>|<span data-ttu-id="7b38b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b38b-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7b38b-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b38b-109">S_OK</span></span>|<span data-ttu-id="7b38b-110">El tiempo de ejecución se desenreda correctamente al marco siguiente (vea comentarios).</span><span class="sxs-lookup"><span data-stu-id="7b38b-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="7b38b-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7b38b-111">E_FAIL</span></span>|<span data-ttu-id="7b38b-112">El `ICorDebugStackWalk` no se pudo avanzar el objeto.</span><span class="sxs-lookup"><span data-stu-id="7b38b-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="7b38b-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="7b38b-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="7b38b-114">Se alcanzó el final de la pila como resultado de este desenredo.</span><span class="sxs-lookup"><span data-stu-id="7b38b-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="7b38b-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="7b38b-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="7b38b-116">El puntero de marco ya está al final de la pila; por lo tanto, no puede tener acceso a ningún marco adicional.</span><span class="sxs-lookup"><span data-stu-id="7b38b-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="7b38b-117">Excepciones</span><span class="sxs-lookup"><span data-stu-id="7b38b-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b38b-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7b38b-118">Remarks</span></span>  
 <span data-ttu-id="7b38b-119">El `Next` método avances el `ICorDebugStackWalk` objeto al marco de llamada solo si el runtime puede desenredar el marco actual.</span><span class="sxs-lookup"><span data-stu-id="7b38b-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="7b38b-120">En caso contrario, el objeto avanza al siguiente fotograma que el tiempo de ejecución es capaz de desenredo.</span><span class="sxs-lookup"><span data-stu-id="7b38b-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b38b-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b38b-121">Requirements</span></span>  
 <span data-ttu-id="7b38b-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b38b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b38b-123">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b38b-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b38b-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b38b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b38b-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b38b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b38b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b38b-126">See also</span></span>
- [<span data-ttu-id="7b38b-127">ICorDebugStackWalk (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b38b-127">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [<span data-ttu-id="7b38b-128">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7b38b-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7b38b-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="7b38b-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
