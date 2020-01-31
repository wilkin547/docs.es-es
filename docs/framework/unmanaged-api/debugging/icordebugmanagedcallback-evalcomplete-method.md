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
ms.openlocfilehash: d29f4095a1d615285f4c4ff30e36b91404036949
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788412"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="54893-102">ICorDebugManagedCallback::EvalComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="54893-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="54893-103">Notifica al depurador que se ha completado una evaluación.</span><span class="sxs-lookup"><span data-stu-id="54893-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54893-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54893-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54893-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="54893-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="54893-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se realizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="54893-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="54893-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se realizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="54893-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="54893-108">de Un puntero a un objeto ICorDebugEval que representa el código que llevó a cabo la evaluación.</span><span class="sxs-lookup"><span data-stu-id="54893-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54893-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="54893-109">Requirements</span></span>  
 <span data-ttu-id="54893-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54893-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54893-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54893-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54893-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54893-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54893-113">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54893-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54893-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="54893-114">See also</span></span>

- [<span data-ttu-id="54893-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="54893-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
