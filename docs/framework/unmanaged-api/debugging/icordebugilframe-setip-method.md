---
title: "ICorDebugILFrame::SetIP (Método)"
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
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: daffbbd9e961f4fdc7ff2e3c9be57e41e8fa3f78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="50c63-102">ICorDebugILFrame::SetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="50c63-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="50c63-103">Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código de lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="50c63-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50c63-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50c63-104">Syntax</span></span>  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50c63-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="50c63-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="50c63-106">La ubicación de desplazamiento en el código MSIL.</span><span class="sxs-lookup"><span data-stu-id="50c63-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50c63-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="50c63-107">Remarks</span></span>  
 <span data-ttu-id="50c63-108">Las llamadas a `SetIP` inmediatamente invalidar todos los marcos y cadenas para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="50c63-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="50c63-109">Si el depurador necesita información del marco después de llamar a `SetIP`, debe realizar un seguimiento de pila nueva.</span><span class="sxs-lookup"><span data-stu-id="50c63-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="50c63-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) intentará mantener el marco de pila en un estado válido.</span><span class="sxs-lookup"><span data-stu-id="50c63-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="50c63-111">Sin embargo, incluso si el marco está en un estado válido, todavía puede haber problemas, como variables locales sin inicializar.</span><span class="sxs-lookup"><span data-stu-id="50c63-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="50c63-112">El llamador es responsable de garantizar la coherencia del programa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="50c63-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="50c63-113">En plataformas de 64 bits, no se puede mover el puntero de instrucción fuera de un `catch` o `finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="50c63-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="50c63-114">Si `SetIP` se llama para hacer ese cambio en una plataforma de 64 bits, devolverá un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="50c63-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50c63-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50c63-115">Requirements</span></span>  
 <span data-ttu-id="50c63-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50c63-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50c63-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50c63-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50c63-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50c63-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50c63-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50c63-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
