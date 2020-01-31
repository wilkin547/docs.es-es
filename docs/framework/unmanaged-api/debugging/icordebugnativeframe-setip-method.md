---
title: ICorDebugNativeFrame::SetIP (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
ms.openlocfilehash: bc33768e4155a0e272d3374d4c586c79ef2ff3fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792778"
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="a80ea-102">ICorDebugNativeFrame::SetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="a80ea-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="a80ea-103">Establece el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.</span><span class="sxs-lookup"><span data-stu-id="a80ea-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a80ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a80ea-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a80ea-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="a80ea-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="a80ea-106">de Ubicación de desplazamiento en el código nativo.</span><span class="sxs-lookup"><span data-stu-id="a80ea-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a80ea-107">Notas</span><span class="sxs-lookup"><span data-stu-id="a80ea-107">Remarks</span></span>  
 <span data-ttu-id="a80ea-108">Las llamadas a `SetIP` invalidan inmediatamente todos los marcos y cadenas para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a80ea-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="a80ea-109">Si el depurador necesita información de fotogramas después de una llamada a `SetIP`, debe realizar un nuevo seguimiento de la pila.</span><span class="sxs-lookup"><span data-stu-id="a80ea-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="a80ea-110">[ICorDebug](icordebug-interface.md) intentará mantener el marco de pila en un estado válido.</span><span class="sxs-lookup"><span data-stu-id="a80ea-110">[ICorDebug](icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="a80ea-111">Sin embargo, aunque el marco esté en un estado válido, en lo que se refiere al tiempo de ejecución, todavía puede haber problemas, como variables locales sin inicializar, etc.</span><span class="sxs-lookup"><span data-stu-id="a80ea-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="a80ea-112">El autor de la llamada es responsable de garantizar la coherencia del programa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="a80ea-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="a80ea-113">En las plataformas de 64 bits, el puntero de instrucción no se puede sacar de un bloque `catch` o `finally`.</span><span class="sxs-lookup"><span data-stu-id="a80ea-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="a80ea-114">Si se llama a `SetIP` para hacer este movimiento en una plataforma de 64 bits, devolverá un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="a80ea-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a80ea-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="a80ea-115">Requirements</span></span>  
 <span data-ttu-id="a80ea-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a80ea-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a80ea-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a80ea-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a80ea-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a80ea-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a80ea-119">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a80ea-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a80ea-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a80ea-120">See also</span></span>
