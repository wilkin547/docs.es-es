---
description: 'Más información sobre: ICorDebugStackWalk:: SetContext (método)'
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
ms.openlocfilehash: 20e18460d237a63e4c2695b9e7cbfa766ed3908f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794720"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="f2282-103">ICorDebugStackWalk::SetContext (Método)</span><span class="sxs-lookup"><span data-stu-id="f2282-103">ICorDebugStackWalk::SetContext Method</span></span>

<span data-ttu-id="f2282-104">Establece el contexto actual del objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) en un contexto válido para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="f2282-104">Sets the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2282-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2282-105">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2282-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2282-106">Parameters</span></span>  

 `flag`  
 <span data-ttu-id="f2282-107">de Marca [CorDebugSetContextFlag (](cordebugsetcontextflag-enumeration.md) que indica si el contexto procede del marco activo de la pila o un contexto obtenido al desenredar la pila.</span><span class="sxs-lookup"><span data-stu-id="f2282-107">[in] A [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="f2282-108">de Tamaño asignado del `CONTEXT` búfer.</span><span class="sxs-lookup"><span data-stu-id="f2282-108">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="f2282-109">de `CONTEXT` Búfer.</span><span class="sxs-lookup"><span data-stu-id="f2282-109">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2282-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f2282-110">Return Value</span></span>  

 <span data-ttu-id="f2282-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="f2282-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f2282-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2282-112">HRESULT</span></span>|<span data-ttu-id="f2282-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2282-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2282-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2282-114">S_OK</span></span>|<span data-ttu-id="f2282-115">El `ICorDebugStackWalk` contexto del objeto se estableció correctamente.</span><span class="sxs-lookup"><span data-stu-id="f2282-115">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="f2282-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f2282-116">E_FAIL</span></span>|<span data-ttu-id="f2282-117">`ICorDebugStackWalk`No se ha establecido el contexto del objeto.</span><span class="sxs-lookup"><span data-stu-id="f2282-117">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="f2282-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f2282-118">E_INVALIDARG</span></span>|<span data-ttu-id="f2282-119">El contexto es una null.</span><span class="sxs-lookup"><span data-stu-id="f2282-119">The context is null.</span></span>|  
|<span data-ttu-id="f2282-120">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="f2282-120">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="f2282-121">El búfer de contexto es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="f2282-121">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="f2282-122">Excepciones</span><span class="sxs-lookup"><span data-stu-id="f2282-122">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2282-123">Notas</span><span class="sxs-lookup"><span data-stu-id="f2282-123">Remarks</span></span>  

 <span data-ttu-id="f2282-124">Este método no modifica el contexto actual del subproceso.</span><span class="sxs-lookup"><span data-stu-id="f2282-124">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="f2282-125">Establecer el contexto actual en un contexto no válido puede producir resultados imprevisibles del rastreador de pila.</span><span class="sxs-lookup"><span data-stu-id="f2282-125">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="f2282-126">Puede recuperar una copia bit a bit exacta de este contexto llamando inmediatamente al método [ICorDebugStackWalk:: getContext](icordebugstackwalk-getcontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f2282-126">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2282-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2282-127">Requirements</span></span>  

 <span data-ttu-id="f2282-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2282-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2282-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2282-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2282-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2282-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2282-131">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2282-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2282-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2282-132">See also</span></span>

- [<span data-ttu-id="f2282-133">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f2282-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f2282-134">Depuración</span><span class="sxs-lookup"><span data-stu-id="f2282-134">Debugging</span></span>](index.md)
