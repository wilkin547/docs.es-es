---
title: ICorDebugManagedCallback::EvalException (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type:
- apiref
ms.openlocfilehash: 70ae72968c3411a6732b09c0afe3d82931410cb5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130814"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="732b3-102">ICorDebugManagedCallback::EvalException (Método)</span><span class="sxs-lookup"><span data-stu-id="732b3-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="732b3-103">Notifica al depurador que una evaluación ha finalizado con una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="732b3-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="732b3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="732b3-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="732b3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="732b3-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="732b3-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que finalizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="732b3-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="732b3-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que finalizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="732b3-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="732b3-108">de Un puntero a un objeto ICorDebugEval que representa el código que llevó a cabo la evaluación.</span><span class="sxs-lookup"><span data-stu-id="732b3-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="732b3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="732b3-109">Requirements</span></span>  
 <span data-ttu-id="732b3-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="732b3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="732b3-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="732b3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="732b3-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="732b3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="732b3-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="732b3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="732b3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="732b3-114">See also</span></span>

- [<span data-ttu-id="732b3-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="732b3-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
