---
title: ICorDebugEval2::RudeAbort (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.RudeAbort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::RudeAbort
helpviewer_keywords:
- ICorDebugEval2::RudeAbort method [.NET Framework debugging]
- RudeAbort method, ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: 02468edf-d32b-4cb3-aaa8-3dd2abfc8b25
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a1adb79e5081fc909d0cd180d8161eccea7e58e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754353"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="ecd7e-102">ICorDebugEval2::RudeAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="ecd7e-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="ecd7e-103">Anula el cálculo que `ICorDebugEval2` está realizando actualmente.</span><span class="sxs-lookup"><span data-stu-id="ecd7e-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecd7e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecd7e-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ecd7e-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ecd7e-105">Remarks</span></span>  
 <span data-ttu-id="ecd7e-106">`RudeAbort` no libera los bloqueos que mantiene el evaluador, por lo que deja la sesión de depuración en un estado no seguro.</span><span class="sxs-lookup"><span data-stu-id="ecd7e-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="ecd7e-107">Llame a este método con extrema precaución.</span><span class="sxs-lookup"><span data-stu-id="ecd7e-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecd7e-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ecd7e-108">Requirements</span></span>  
 <span data-ttu-id="ecd7e-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecd7e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecd7e-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecd7e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecd7e-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecd7e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecd7e-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecd7e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
