---
description: 'Más información acerca de: ICorDebugStackWalk:: GetContext (método)'
title: ICorDebugStackWalk::GetContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
ms.openlocfilehash: 30beefaa1e0e2e4c5043cae7213658ac24e8a1b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649616"
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="902db-103">ICorDebugStackWalk::GetContext (Método)</span><span class="sxs-lookup"><span data-stu-id="902db-103">ICorDebugStackWalk::GetContext Method</span></span>

<span data-ttu-id="902db-104">Devuelve el contexto del marco actual del objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="902db-104">Returns the context for the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="902db-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="902db-105">Syntax</span></span>  
  
```cpp  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="902db-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="902db-106">Parameters</span></span>  

 `contextFlags`  
 <span data-ttu-id="902db-107">de Marcas que indican el contenido solicitado del búfer de contexto (definido en Winnt. h).</span><span class="sxs-lookup"><span data-stu-id="902db-107">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="902db-108">de Tamaño asignado del búfer de contexto.</span><span class="sxs-lookup"><span data-stu-id="902db-108">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="902db-109">enuncia Tamaño real del contexto.</span><span class="sxs-lookup"><span data-stu-id="902db-109">[out] The actual size of the context.</span></span> <span data-ttu-id="902db-110">Este valor debe ser menor o igual que el tamaño del búfer de contexto.</span><span class="sxs-lookup"><span data-stu-id="902db-110">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="902db-111">enuncia Búfer de contexto.</span><span class="sxs-lookup"><span data-stu-id="902db-111">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="902db-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="902db-112">Return Value</span></span>  

 <span data-ttu-id="902db-113">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="902db-113">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="902db-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="902db-114">HRESULT</span></span>|<span data-ttu-id="902db-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="902db-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="902db-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="902db-116">S_OK</span></span>|<span data-ttu-id="902db-117">El contexto del marco actual se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="902db-117">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="902db-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="902db-118">E_FAIL</span></span>|<span data-ttu-id="902db-119">No se pudo devolver el contexto.</span><span class="sxs-lookup"><span data-stu-id="902db-119">The context could not be returned.</span></span>|  
|<span data-ttu-id="902db-120">HRESULT_FROM_WIN32 (BÚFER DE ERROR_INSUFFICIENT)</span><span class="sxs-lookup"><span data-stu-id="902db-120">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="902db-121">El búfer de contexto es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="902db-121">The context buffer is too small.</span></span>|  
|<span data-ttu-id="902db-122">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="902db-122">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="902db-123">El puntero de marco ya está al final de la pila; por lo tanto, no se puede tener acceso a ningún fotograma adicional.</span><span class="sxs-lookup"><span data-stu-id="902db-123">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="902db-124">Excepciones</span><span class="sxs-lookup"><span data-stu-id="902db-124">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="902db-125">Notas</span><span class="sxs-lookup"><span data-stu-id="902db-125">Remarks</span></span>  

 <span data-ttu-id="902db-126">Dado que el desenredado solo restaura un subconjunto de los registros, como los registros no volátiles, es posible que el contexto no coincida exactamente con el estado del registro en el momento de la llamada.</span><span class="sxs-lookup"><span data-stu-id="902db-126">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="902db-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="902db-127">Requirements</span></span>  

 <span data-ttu-id="902db-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="902db-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="902db-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="902db-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="902db-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="902db-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="902db-131">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="902db-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="902db-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="902db-132">See also</span></span>

- [<span data-ttu-id="902db-133">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="902db-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="902db-134">Depuración</span><span class="sxs-lookup"><span data-stu-id="902db-134">Debugging</span></span>](index.md)
