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
ms.openlocfilehash: 8cebb66ecf298eaaca0e7af23a9b8c6a2932c23f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131828"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="09c7f-102">ICorDebugStackWalk::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="09c7f-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="09c7f-103">Mueve el objeto [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) al siguiente fotograma.</span><span class="sxs-lookup"><span data-stu-id="09c7f-103">Moves the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09c7f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09c7f-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="09c7f-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="09c7f-105">Return Value</span></span>  
 <span data-ttu-id="09c7f-106">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="09c7f-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="09c7f-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09c7f-107">HRESULT</span></span>|<span data-ttu-id="09c7f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="09c7f-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09c7f-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="09c7f-109">S_OK</span></span>|<span data-ttu-id="09c7f-110">El tiempo de ejecución se desenrollará correctamente en el siguiente fotograma (vea la sección comentarios).</span><span class="sxs-lookup"><span data-stu-id="09c7f-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="09c7f-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="09c7f-111">E_FAIL</span></span>|<span data-ttu-id="09c7f-112">No se pudo modificar el objeto de `ICorDebugStackWalk`.</span><span class="sxs-lookup"><span data-stu-id="09c7f-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="09c7f-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="09c7f-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="09c7f-114">Se alcanzó el final de la pila como resultado de este desenredado.</span><span class="sxs-lookup"><span data-stu-id="09c7f-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="09c7f-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="09c7f-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="09c7f-116">El puntero de marco ya está al final de la pila; por lo tanto, no se puede tener acceso a ningún fotograma adicional.</span><span class="sxs-lookup"><span data-stu-id="09c7f-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="09c7f-117">Excepciones</span><span class="sxs-lookup"><span data-stu-id="09c7f-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09c7f-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="09c7f-118">Remarks</span></span>  
 <span data-ttu-id="09c7f-119">El método `Next` desplaza el objeto `ICorDebugStackWalk` al marco que realiza la llamada solo si el tiempo de ejecución puede desenredar el fotograma actual.</span><span class="sxs-lookup"><span data-stu-id="09c7f-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="09c7f-120">De lo contrario, el objeto avanza hasta el siguiente fotograma que el runtime puede desenredar.</span><span class="sxs-lookup"><span data-stu-id="09c7f-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09c7f-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09c7f-121">Requirements</span></span>  
 <span data-ttu-id="09c7f-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09c7f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09c7f-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09c7f-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09c7f-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09c7f-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09c7f-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09c7f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09c7f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="09c7f-126">See also</span></span>

- [<span data-ttu-id="09c7f-127">ICorDebugStackWalk (interfaz)</span><span class="sxs-lookup"><span data-stu-id="09c7f-127">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [<span data-ttu-id="09c7f-128">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="09c7f-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="09c7f-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="09c7f-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
