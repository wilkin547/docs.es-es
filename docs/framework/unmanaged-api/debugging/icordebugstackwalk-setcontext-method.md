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
ms.openlocfilehash: 1ae9fc1f1154866945d40cd63042fa8a43b88905
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677302"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="cee11-102">ICorDebugStackWalk::SetContext (Método)</span><span class="sxs-lookup"><span data-stu-id="cee11-102">ICorDebugStackWalk::SetContext Method</span></span>

<span data-ttu-id="cee11-103">Establece el contexto actual del objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) en un contexto válido para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="cee11-103">Sets the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cee11-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cee11-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cee11-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cee11-105">Parameters</span></span>  

 `flag`  
 <span data-ttu-id="cee11-106">de Marca [CorDebugSetContextFlag (](cordebugsetcontextflag-enumeration.md) que indica si el contexto procede del marco activo de la pila o un contexto obtenido al desenredar la pila.</span><span class="sxs-lookup"><span data-stu-id="cee11-106">[in] A [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="cee11-107">de Tamaño asignado del `CONTEXT` búfer.</span><span class="sxs-lookup"><span data-stu-id="cee11-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="cee11-108">de `CONTEXT` Búfer.</span><span class="sxs-lookup"><span data-stu-id="cee11-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cee11-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cee11-109">Return Value</span></span>  

 <span data-ttu-id="cee11-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="cee11-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="cee11-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cee11-111">HRESULT</span></span>|<span data-ttu-id="cee11-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="cee11-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cee11-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="cee11-113">S_OK</span></span>|<span data-ttu-id="cee11-114">El `ICorDebugStackWalk` contexto del objeto se estableció correctamente.</span><span class="sxs-lookup"><span data-stu-id="cee11-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="cee11-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cee11-115">E_FAIL</span></span>|<span data-ttu-id="cee11-116">`ICorDebugStackWalk`No se ha establecido el contexto del objeto.</span><span class="sxs-lookup"><span data-stu-id="cee11-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="cee11-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="cee11-117">E_INVALIDARG</span></span>|<span data-ttu-id="cee11-118">El contexto es una null.</span><span class="sxs-lookup"><span data-stu-id="cee11-118">The context is null.</span></span>|  
|<span data-ttu-id="cee11-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="cee11-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="cee11-120">El búfer de contexto es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="cee11-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="cee11-121">Excepciones</span><span class="sxs-lookup"><span data-stu-id="cee11-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cee11-122">Notas</span><span class="sxs-lookup"><span data-stu-id="cee11-122">Remarks</span></span>  

 <span data-ttu-id="cee11-123">Este método no modifica el contexto actual del subproceso.</span><span class="sxs-lookup"><span data-stu-id="cee11-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="cee11-124">Establecer el contexto actual en un contexto no válido puede producir resultados imprevisibles del rastreador de pila.</span><span class="sxs-lookup"><span data-stu-id="cee11-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="cee11-125">Puede recuperar una copia bit a bit exacta de este contexto llamando inmediatamente al método [ICorDebugStackWalk:: getContext](icordebugstackwalk-getcontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cee11-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cee11-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cee11-126">Requirements</span></span>  

 <span data-ttu-id="cee11-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cee11-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cee11-128">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cee11-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cee11-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cee11-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cee11-130">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cee11-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cee11-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cee11-131">See also</span></span>

- [<span data-ttu-id="cee11-132">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="cee11-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="cee11-133">Depuración</span><span class="sxs-lookup"><span data-stu-id="cee11-133">Debugging</span></span>](index.md)
