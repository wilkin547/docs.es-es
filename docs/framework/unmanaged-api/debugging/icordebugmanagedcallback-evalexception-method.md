---
title: "ICorDebugManagedCallback::EvalException (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.EvalException
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3aa26c9458796dd20af0e22dd4a9961225b59bfc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="7d7f6-102">ICorDebugManagedCallback::EvalException (Método)</span><span class="sxs-lookup"><span data-stu-id="7d7f6-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="7d7f6-103">Notifica al depurador que una evaluación ha finalizado con una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="7d7f6-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d7f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d7f6-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d7f6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d7f6-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7d7f6-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que ha finalizado la evaluación.</span><span class="sxs-lookup"><span data-stu-id="7d7f6-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="7d7f6-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que ha finalizado la evaluación.</span><span class="sxs-lookup"><span data-stu-id="7d7f6-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="7d7f6-108">[in] Un puntero a un objeto ICorDebugEval que representa el código que realiza la evaluación.</span><span class="sxs-lookup"><span data-stu-id="7d7f6-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d7f6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d7f6-109">Requirements</span></span>  
 <span data-ttu-id="7d7f6-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d7f6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d7f6-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d7f6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d7f6-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d7f6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d7f6-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d7f6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d7f6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d7f6-114">See Also</span></span>  
 [<span data-ttu-id="7d7f6-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d7f6-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
