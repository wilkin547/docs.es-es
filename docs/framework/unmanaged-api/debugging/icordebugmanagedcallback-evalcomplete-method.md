---
title: ICorDebugManagedCallback::EvalComplete (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type:
- apiref
ms.openlocfilehash: d52c19f8663a776215241ddb16f3aa9ba00c0d36
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137349"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="48115-102">ICorDebugManagedCallback::EvalComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="48115-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="48115-103">Notifica al depurador que se ha completado una evaluación.</span><span class="sxs-lookup"><span data-stu-id="48115-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48115-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48115-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48115-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48115-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="48115-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se realizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="48115-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="48115-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se realizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="48115-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="48115-108">de Un puntero a un objeto ICorDebugEval que representa el código que llevó a cabo la evaluación.</span><span class="sxs-lookup"><span data-stu-id="48115-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48115-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48115-109">Requirements</span></span>  
 <span data-ttu-id="48115-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48115-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48115-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48115-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48115-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48115-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48115-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48115-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48115-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="48115-114">See also</span></span>

- [<span data-ttu-id="48115-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48115-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
