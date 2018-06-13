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
ms.openlocfilehash: 688c5a4b5a18cea444ebf1d63f3ea012a5d815c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415215"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="f2207-102">ICorDebugManagedCallback::EvalComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="f2207-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="f2207-103">Notifica al depurador que se ha completado una evaluación.</span><span class="sxs-lookup"><span data-stu-id="f2207-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2207-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2207-104">Syntax</span></span>  
  
```  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2207-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2207-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="f2207-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se realizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="f2207-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="f2207-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se realizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="f2207-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="f2207-108">[in] Un puntero a un objeto ICorDebugEval que representa el código que realiza la evaluación.</span><span class="sxs-lookup"><span data-stu-id="f2207-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2207-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2207-109">Requirements</span></span>  
 <span data-ttu-id="f2207-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2207-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2207-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2207-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2207-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2207-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2207-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2207-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2207-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2207-114">See Also</span></span>  
 [<span data-ttu-id="f2207-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2207-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
