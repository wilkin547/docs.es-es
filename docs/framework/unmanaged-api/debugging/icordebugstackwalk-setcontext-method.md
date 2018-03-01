---
title: "ICorDebugStackWalk::SetContext (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 00e278df2b23d6fddb18c24eefb3f2aa4d1cc3cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="3b917-102">ICorDebugStackWalk::SetContext (Método)</span><span class="sxs-lookup"><span data-stu-id="3b917-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="3b917-103">Establece el [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) contexto actual del objeto en un contexto válido para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="3b917-103">Sets the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b917-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b917-104">Syntax</span></span>  
  
```  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b917-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b917-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="3b917-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) marca que indica si el contexto procede del marco activo de la pila o un contexto obtenido desenredando la pila.</span><span class="sxs-lookup"><span data-stu-id="3b917-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="3b917-107">[in] El tamaño asignado de la `CONTEXT` búfer.</span><span class="sxs-lookup"><span data-stu-id="3b917-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="3b917-108">[in] El `CONTEXT` búfer.</span><span class="sxs-lookup"><span data-stu-id="3b917-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b917-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3b917-109">Return Value</span></span>  
 <span data-ttu-id="3b917-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="3b917-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3b917-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3b917-111">HRESULT</span></span>|<span data-ttu-id="3b917-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b917-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3b917-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="3b917-113">S_OK</span></span>|<span data-ttu-id="3b917-114">El `ICorDebugStackWalk` contexto del objeto se estableció correctamente.</span><span class="sxs-lookup"><span data-stu-id="3b917-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="3b917-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3b917-115">E_FAIL</span></span>|<span data-ttu-id="3b917-116">El `ICorDebugStackWalk` no se estableció el contexto del objeto.</span><span class="sxs-lookup"><span data-stu-id="3b917-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="3b917-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3b917-117">E_INVALIDARG</span></span>|<span data-ttu-id="3b917-118">El contexto es null.</span><span class="sxs-lookup"><span data-stu-id="3b917-118">The context is null.</span></span>|  
|<span data-ttu-id="3b917-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="3b917-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="3b917-120">El búfer de contexto es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="3b917-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="3b917-121">Excepciones</span><span class="sxs-lookup"><span data-stu-id="3b917-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b917-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b917-122">Remarks</span></span>  
 <span data-ttu-id="3b917-123">Este método no modifica el contexto actual del subproceso.</span><span class="sxs-lookup"><span data-stu-id="3b917-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="3b917-124">Si se establece el contexto actual en un contexto no válido puede provocar resultados imprevisibles desde el Rastreador de pila.</span><span class="sxs-lookup"><span data-stu-id="3b917-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="3b917-125">Puede recuperar una copia bit a bit exacta de este contexto llamando inmediatamente la [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="3b917-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b917-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b917-126">Requirements</span></span>  
 <span data-ttu-id="3b917-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b917-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b917-128">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b917-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b917-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b917-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b917-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b917-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b917-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b917-131">See Also</span></span>  
 [<span data-ttu-id="3b917-132">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3b917-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="3b917-133">Depuración</span><span class="sxs-lookup"><span data-stu-id="3b917-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
