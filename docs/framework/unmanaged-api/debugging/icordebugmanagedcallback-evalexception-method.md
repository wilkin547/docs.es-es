---
description: 'Más información acerca de: ICorDebugManagedCallback:: EvalException ((método)'
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
ms.openlocfilehash: 0938276a854020efa897499af8c0fd69c0541124
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790989"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="de509-103">ICorDebugManagedCallback::EvalException (Método)</span><span class="sxs-lookup"><span data-stu-id="de509-103">ICorDebugManagedCallback::EvalException Method</span></span>

<span data-ttu-id="de509-104">Notifica al depurador que una evaluación ha finalizado con una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="de509-104">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de509-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de509-105">Syntax</span></span>  
  
```cpp  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de509-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="de509-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="de509-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que finalizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="de509-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="de509-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que finalizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="de509-108">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="de509-109">de Un puntero a un objeto ICorDebugEval que representa el código que llevó a cabo la evaluación.</span><span class="sxs-lookup"><span data-stu-id="de509-109">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de509-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de509-110">Requirements</span></span>  

 <span data-ttu-id="de509-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de509-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de509-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de509-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de509-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de509-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de509-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de509-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de509-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="de509-115">See also</span></span>

- [<span data-ttu-id="de509-116">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="de509-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
