---
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
ms.openlocfilehash: 0d36390a905561b64b3ca6ca95722f82158450be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695223"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="fc625-102">ICorDebugProcess::ClearCurrentException (Método)</span><span class="sxs-lookup"><span data-stu-id="fc625-102">ICorDebugProcess::ClearCurrentException Method</span></span>

<span data-ttu-id="fc625-103">Borra la excepción no administrada actual en el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="fc625-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc625-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc625-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc625-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc625-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="fc625-106">de IDENTIFICADOR del subproceso en el que se borrará la excepción no administrada actual.</span><span class="sxs-lookup"><span data-stu-id="fc625-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc625-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc625-107">Remarks</span></span>  

 <span data-ttu-id="fc625-108">Llame a este método antes de llamar a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) cuando un subproceso haya comunicado una excepción no administrada que el código depurado debe omitir.</span><span class="sxs-lookup"><span data-stu-id="fc625-108">Call this method before calling [ICorDebugController::Continue](icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="fc625-109">Esto borrará los eventos en banda (IB) y fuera de banda (OOB) pendientes en el subproceso determinado.</span><span class="sxs-lookup"><span data-stu-id="fc625-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="fc625-110">Todos los puntos de interrupción de OOB y las excepciones de un solo paso se borran automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fc625-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="fc625-111">Use [ICorDebugThread2:: interceptcurrentexception (](icordebugthread2-interceptcurrentexception-method.md) para interceptar la excepción administrada actual en un subproceso.</span><span class="sxs-lookup"><span data-stu-id="fc625-111">Use [ICorDebugThread2::InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc625-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc625-112">Requirements</span></span>  

 <span data-ttu-id="fc625-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc625-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc625-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc625-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc625-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc625-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc625-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc625-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
