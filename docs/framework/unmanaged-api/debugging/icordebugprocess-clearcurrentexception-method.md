---
description: 'Más información acerca de: ICorDebugProcess:: ClearCurrentException ((método)'
title: ICorDebugProcess::ClearCurrentException (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
ms.openlocfilehash: 6f356078d8d303acb39cbaa500b7592185ad55ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754048"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="15589-103">ICorDebugProcess::ClearCurrentException (Método)</span><span class="sxs-lookup"><span data-stu-id="15589-103">ICorDebugProcess::ClearCurrentException Method</span></span>

<span data-ttu-id="15589-104">Borra la excepción no administrada actual en el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="15589-104">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15589-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15589-105">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15589-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15589-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="15589-107">de IDENTIFICADOR del subproceso en el que se borrará la excepción no administrada actual.</span><span class="sxs-lookup"><span data-stu-id="15589-107">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15589-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="15589-108">Remarks</span></span>  

 <span data-ttu-id="15589-109">Llame a este método antes de llamar a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) cuando un subproceso haya comunicado una excepción no administrada que el código depurado debe omitir.</span><span class="sxs-lookup"><span data-stu-id="15589-109">Call this method before calling [ICorDebugController::Continue](icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="15589-110">Esto borrará los eventos en banda (IB) y fuera de banda (OOB) pendientes en el subproceso determinado.</span><span class="sxs-lookup"><span data-stu-id="15589-110">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="15589-111">Todos los puntos de interrupción de OOB y las excepciones de un solo paso se borran automáticamente.</span><span class="sxs-lookup"><span data-stu-id="15589-111">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="15589-112">Use [ICorDebugThread2:: interceptcurrentexception (](icordebugthread2-interceptcurrentexception-method.md) para interceptar la excepción administrada actual en un subproceso.</span><span class="sxs-lookup"><span data-stu-id="15589-112">Use [ICorDebugThread2::InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15589-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15589-113">Requirements</span></span>  

 <span data-ttu-id="15589-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15589-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15589-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15589-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15589-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15589-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15589-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15589-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
