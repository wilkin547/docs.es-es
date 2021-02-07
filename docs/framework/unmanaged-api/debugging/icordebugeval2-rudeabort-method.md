---
description: 'Más información sobre: ICorDebugEval2:: RudeAbort ((método)'
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
ms.openlocfilehash: 2835fd635da007b5ee3f0e642b77f3954945f168
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693517"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="48959-103">ICorDebugEval2::RudeAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="48959-103">ICorDebugEval2::RudeAbort Method</span></span>

<span data-ttu-id="48959-104">Anula el cálculo que `ICorDebugEval2` está realizando actualmente.</span><span class="sxs-lookup"><span data-stu-id="48959-104">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48959-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48959-105">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="48959-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="48959-106">Remarks</span></span>  

 <span data-ttu-id="48959-107">`RudeAbort` no libera los bloqueos que mantiene el evaluador, por lo que deja la sesión de depuración en un estado no seguro.</span><span class="sxs-lookup"><span data-stu-id="48959-107">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="48959-108">Llame a este método con sumo cuidado.</span><span class="sxs-lookup"><span data-stu-id="48959-108">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48959-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48959-109">Requirements</span></span>  

 <span data-ttu-id="48959-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48959-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48959-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48959-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48959-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48959-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48959-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48959-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
