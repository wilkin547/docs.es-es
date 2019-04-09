---
title: ICorDebugStackWalk::SetContext (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7306ee61d750ae256c93c049819a23d3d61f7297
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116472"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="b20c9-102">ICorDebugStackWalk::SetContext (Método)</span><span class="sxs-lookup"><span data-stu-id="b20c9-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="b20c9-103">Establece el [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) contexto actual del objeto en un contexto válido para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="b20c9-103">Sets the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b20c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b20c9-104">Syntax</span></span>  
  
```  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b20c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b20c9-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="b20c9-106">[in] Un [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) marca que indica si el contexto procede del marco activo de la pila o un contexto obtenido desenredando la pila.</span><span class="sxs-lookup"><span data-stu-id="b20c9-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="b20c9-107">[in] El tamaño asignado de la `CONTEXT` búfer.</span><span class="sxs-lookup"><span data-stu-id="b20c9-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="b20c9-108">[in] El `CONTEXT` búfer.</span><span class="sxs-lookup"><span data-stu-id="b20c9-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b20c9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b20c9-109">Return Value</span></span>  
 <span data-ttu-id="b20c9-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="b20c9-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b20c9-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b20c9-111">HRESULT</span></span>|<span data-ttu-id="b20c9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b20c9-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b20c9-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b20c9-113">S_OK</span></span>|<span data-ttu-id="b20c9-114">El `ICorDebugStackWalk` contexto del objeto se ha establecido correctamente.</span><span class="sxs-lookup"><span data-stu-id="b20c9-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="b20c9-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b20c9-115">E_FAIL</span></span>|<span data-ttu-id="b20c9-116">El `ICorDebugStackWalk` no se ha establecido el contexto del objeto.</span><span class="sxs-lookup"><span data-stu-id="b20c9-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="b20c9-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b20c9-117">E_INVALIDARG</span></span>|<span data-ttu-id="b20c9-118">El contexto es null.</span><span class="sxs-lookup"><span data-stu-id="b20c9-118">The context is null.</span></span>|  
|<span data-ttu-id="b20c9-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="b20c9-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="b20c9-120">El búfer de contexto es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="b20c9-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="b20c9-121">Excepciones</span><span class="sxs-lookup"><span data-stu-id="b20c9-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b20c9-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b20c9-122">Remarks</span></span>  
 <span data-ttu-id="b20c9-123">Este método no modifica el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="b20c9-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="b20c9-124">Establecer el contexto actual en un contexto no válido, puede producir resultados imprevisibles desde el Rastreador de pila.</span><span class="sxs-lookup"><span data-stu-id="b20c9-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="b20c9-125">Puede recuperar una copia bit a bit exacta de este contexto llamando inmediatamente el [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b20c9-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b20c9-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b20c9-126">Requirements</span></span>  
 <span data-ttu-id="b20c9-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b20c9-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b20c9-128">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b20c9-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b20c9-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b20c9-129">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b20c9-130">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b20c9-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b20c9-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="b20c9-131">See also</span></span>

- [<span data-ttu-id="b20c9-132">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="b20c9-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b20c9-133">Depuración</span><span class="sxs-lookup"><span data-stu-id="b20c9-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
