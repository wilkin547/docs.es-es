---
title: "ICorDebugVirtualUnwinder::GetContext (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 45a914005e84d33b39d72fce96679e275b921d3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvirtualunwindergetcontext-method"></a><span data-ttu-id="fe6ef-102">ICorDebugVirtualUnwinder::GetContext (método)</span><span class="sxs-lookup"><span data-stu-id="fe6ef-102">ICorDebugVirtualUnwinder::GetContext Method</span></span>
<span data-ttu-id="fe6ef-103">Obtiene el contexto actual de este responsable del desenredado.</span><span class="sxs-lookup"><span data-stu-id="fe6ef-103">Gets the current context of this unwinder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe6ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe6ef-104">Syntax</span></span>  
  
```  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe6ef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe6ef-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="fe6ef-106">[in] Marcas que indican qué partes del contexto se devuelven (definidas en WinNT.h).</span><span class="sxs-lookup"><span data-stu-id="fe6ef-106">[in] Flags that specify which parts of the context to return (defined in WinNT.h).</span></span>  
  
 `cbContextBuf`  
 <span data-ttu-id="fe6ef-107">[in] Número de bytes en `contextBuf`.</span><span class="sxs-lookup"><span data-stu-id="fe6ef-107">[in] The number of bytes in `contextBuf`.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="fe6ef-108">[out] Puntero al número de bytes escritos realmente en `contextBuf`.</span><span class="sxs-lookup"><span data-stu-id="fe6ef-108">[out] A pointer to the number of bytes actually written to `contextBuf`.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="fe6ef-109">[out] Matriz de bytes que contiene el contexto actual de este responsable del desenredado.</span><span class="sxs-lookup"><span data-stu-id="fe6ef-109">[out] A byte array that contains the current context of this unwinder.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe6ef-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fe6ef-110">Return Value</span></span>  
 <span data-ttu-id="fe6ef-111">Cualquier valor HRESULT de error recibido por mscordbi es irrecuperable y hará que las API ICorDebug devuelvan `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="fe6ef-111">Any failing HRESULT value received by mscordbi is considered fatal and will cause ICorDebug APIs to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe6ef-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe6ef-112">Remarks</span></span>  
 <span data-ttu-id="fe6ef-113">Establecer el valor inicial de la `contextBuf` argumento al búfer de contexto devuelto mediante una llamada a la [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="fe6ef-113">You set the initial value of the `contextBuf` argument to the context buffer returned by calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe6ef-114">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fe6ef-114">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="fe6ef-115">Dado que es posible que el desenredado solo restaure un subconjunto de los registros, por ejemplo, solo los registros no volátiles, puede que el contexto no coincida exactamente con el estado del registro en el momento de la llamada al método real.</span><span class="sxs-lookup"><span data-stu-id="fe6ef-115">Because unwinding may only restore a subset of the registers, such as the non-volatile registers only, the context may not exactly match the register state at the time of the actual method call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe6ef-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe6ef-116">Requirements</span></span>  
 <span data-ttu-id="fe6ef-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe6ef-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe6ef-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe6ef-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe6ef-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe6ef-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe6ef-120">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe6ef-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe6ef-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe6ef-121">See Also</span></span>  
 [<span data-ttu-id="fe6ef-122">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe6ef-122">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="fe6ef-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="fe6ef-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
