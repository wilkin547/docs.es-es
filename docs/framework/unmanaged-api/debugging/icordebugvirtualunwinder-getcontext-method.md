---
description: 'Más información sobre: ICorDebugVirtualUnwinder:: GetContext (método)'
title: ICorDebugVirtualUnwinder::GetContext (método)
ms.date: 03/30/2017
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
ms.openlocfilehash: 864f32ce82149658b2d4a617b08e8d7aa41fe642
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790534"
---
# <a name="icordebugvirtualunwindergetcontext-method"></a><span data-ttu-id="0132c-103">ICorDebugVirtualUnwinder::GetContext (método)</span><span class="sxs-lookup"><span data-stu-id="0132c-103">ICorDebugVirtualUnwinder::GetContext Method</span></span>

<span data-ttu-id="0132c-104">Obtiene el contexto actual de este responsable del desenredado.</span><span class="sxs-lookup"><span data-stu-id="0132c-104">Gets the current context of this unwinder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0132c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0132c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0132c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0132c-106">Parameters</span></span>  

 `contextFlags`  
 <span data-ttu-id="0132c-107">[in] Marcas que indican qué partes del contexto se devuelven (definidas en WinNT.h).</span><span class="sxs-lookup"><span data-stu-id="0132c-107">[in] Flags that specify which parts of the context to return (defined in WinNT.h).</span></span>  
  
 `cbContextBuf`  
 <span data-ttu-id="0132c-108">[in] Número de bytes en `contextBuf`.</span><span class="sxs-lookup"><span data-stu-id="0132c-108">[in] The number of bytes in `contextBuf`.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="0132c-109">[out] Puntero al número de bytes escritos realmente en `contextBuf`.</span><span class="sxs-lookup"><span data-stu-id="0132c-109">[out] A pointer to the number of bytes actually written to `contextBuf`.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="0132c-110">[out] Matriz de bytes que contiene el contexto actual de este responsable del desenredado.</span><span class="sxs-lookup"><span data-stu-id="0132c-110">[out] A byte array that contains the current context of this unwinder.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0132c-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0132c-111">Return Value</span></span>  

 <span data-ttu-id="0132c-112">Cualquier valor HRESULT de error recibido por mscordbi es irrecuperable y hará que las API ICorDebug devuelvan `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="0132c-112">Any failing HRESULT value received by mscordbi is considered fatal and will cause ICorDebug APIs to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0132c-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0132c-113">Remarks</span></span>  

 <span data-ttu-id="0132c-114">Establezca el valor inicial del `contextBuf` argumento en el búfer de contexto devuelto mediante una llamada al método [ICorDebugStackWalk:: getContext](icordebugstackwalk-getcontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0132c-114">You set the initial value of the `contextBuf` argument to the context buffer returned by calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0132c-115">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0132c-115">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="0132c-116">Dado que es posible que el desenredado solo restaure un subconjunto de los registros, por ejemplo, solo los registros no volátiles, puede que el contexto no coincida exactamente con el estado del registro en el momento de la llamada al método real.</span><span class="sxs-lookup"><span data-stu-id="0132c-116">Because unwinding may only restore a subset of the registers, such as the non-volatile registers only, the context may not exactly match the register state at the time of the actual method call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0132c-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0132c-117">Requirements</span></span>  

 <span data-ttu-id="0132c-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0132c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0132c-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0132c-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0132c-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0132c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0132c-121">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0132c-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0132c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="0132c-122">See also</span></span>

- [<span data-ttu-id="0132c-123">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="0132c-123">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="0132c-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="0132c-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
