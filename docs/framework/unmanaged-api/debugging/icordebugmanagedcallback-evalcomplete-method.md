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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d5af8196664c63b26f3a10946b69ae922cf13fd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503143"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="e3d67-102">ICorDebugManagedCallback::EvalComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="e3d67-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="e3d67-103">Notifica al depurador que se ha completado una evaluación.</span><span class="sxs-lookup"><span data-stu-id="e3d67-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3d67-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3d67-104">Syntax</span></span>  
  
```  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3d67-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e3d67-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e3d67-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se realizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="e3d67-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="e3d67-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se realizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="e3d67-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="e3d67-108">[in] Un puntero a un objeto ICorDebugEval que representa el código que realiza la evaluación.</span><span class="sxs-lookup"><span data-stu-id="e3d67-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3d67-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3d67-109">Requirements</span></span>  
 <span data-ttu-id="e3d67-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3d67-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3d67-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3d67-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3d67-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3d67-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3d67-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3d67-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3d67-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3d67-114">See also</span></span>
- [<span data-ttu-id="e3d67-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3d67-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
