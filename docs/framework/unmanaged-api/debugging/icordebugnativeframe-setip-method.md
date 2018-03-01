---
title: "ICorDebugNativeFrame::SetIP (Método)"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 25b4f42eb6f10ecade468824d9d790a2bce740a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="a466a-102">ICorDebugNativeFrame::SetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="a466a-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="a466a-103">Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código nativo.</span><span class="sxs-lookup"><span data-stu-id="a466a-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a466a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a466a-104">Syntax</span></span>  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a466a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a466a-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="a466a-106">[in] La ubicación de desplazamiento en el código nativo.</span><span class="sxs-lookup"><span data-stu-id="a466a-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a466a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a466a-107">Remarks</span></span>  
 <span data-ttu-id="a466a-108">Las llamadas a `SetIP` inmediatamente invalidar todos los marcos y cadenas para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a466a-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="a466a-109">Si el depurador necesita información del marco después de llamar a `SetIP`, debe realizar un seguimiento de pila nueva.</span><span class="sxs-lookup"><span data-stu-id="a466a-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="a466a-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) intentará mantener el marco de pila en un estado válido.</span><span class="sxs-lookup"><span data-stu-id="a466a-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="a466a-111">Sin embargo, incluso si el marco está en un estado válido, tal y como lo que se refiere el tiempo de ejecución, todavía puede haber problemas, como variables locales sin inicializar y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="a466a-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="a466a-112">El llamador es responsable de garantizar la coherencia del programa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="a466a-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="a466a-113">En plataformas de 64 bits, no se puede mover el puntero de instrucción fuera de un `catch` o `finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="a466a-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="a466a-114">Si `SetIP` se llama para hacer ese cambio en una plataforma de 64 bits, devolverá un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="a466a-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a466a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a466a-115">Requirements</span></span>  
 <span data-ttu-id="a466a-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a466a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a466a-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a466a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a466a-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a466a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a466a-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a466a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a466a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a466a-120">See Also</span></span>  
 
