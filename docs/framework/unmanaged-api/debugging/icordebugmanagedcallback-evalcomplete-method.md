---
description: 'Más información acerca de: ICorDebugManagedCallback:: Evalcomplete ((método)'
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
ms.openlocfilehash: 729b00bc630ef5d6e508b75bd6483580f1dd75b5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791041"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="15af3-103">ICorDebugManagedCallback::EvalComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="15af3-103">ICorDebugManagedCallback::EvalComplete Method</span></span>

<span data-ttu-id="15af3-104">Notifica al depurador que se ha completado una evaluación.</span><span class="sxs-lookup"><span data-stu-id="15af3-104">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15af3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15af3-105">Syntax</span></span>  
  
```cpp  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15af3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15af3-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="15af3-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se realizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="15af3-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="15af3-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se realizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="15af3-108">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="15af3-109">de Un puntero a un objeto ICorDebugEval que representa el código que llevó a cabo la evaluación.</span><span class="sxs-lookup"><span data-stu-id="15af3-109">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15af3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15af3-110">Requirements</span></span>  

 <span data-ttu-id="15af3-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15af3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15af3-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15af3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15af3-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15af3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15af3-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15af3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15af3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="15af3-115">See also</span></span>

- [<span data-ttu-id="15af3-116">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15af3-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
