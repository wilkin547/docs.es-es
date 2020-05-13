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
ms.openlocfilehash: 20a841006d51671a491e11c4e40287baf739d191
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209830"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="46ef0-102">ICorDebugManagedCallback::EvalException (Método)</span><span class="sxs-lookup"><span data-stu-id="46ef0-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="46ef0-103">Notifica al depurador que una evaluación ha finalizado con una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="46ef0-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46ef0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46ef0-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46ef0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="46ef0-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="46ef0-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que finalizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="46ef0-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="46ef0-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que finalizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="46ef0-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="46ef0-108">de Un puntero a un objeto ICorDebugEval que representa el código que llevó a cabo la evaluación.</span><span class="sxs-lookup"><span data-stu-id="46ef0-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46ef0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46ef0-109">Requirements</span></span>  
 <span data-ttu-id="46ef0-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46ef0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46ef0-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46ef0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46ef0-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46ef0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46ef0-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46ef0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ef0-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46ef0-114">See also</span></span>

- [<span data-ttu-id="46ef0-115">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="46ef0-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
