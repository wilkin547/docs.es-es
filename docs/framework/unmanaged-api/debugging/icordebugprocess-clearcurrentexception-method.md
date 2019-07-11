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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ad7dd3ae0e547933fdf7d579116dccc62ae579c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766149"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="57868-102">ICorDebugProcess::ClearCurrentException (Método)</span><span class="sxs-lookup"><span data-stu-id="57868-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="57868-103">Borra la excepción no administrada actual del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="57868-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57868-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57868-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57868-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57868-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="57868-106">[in] El identificador del subproceso en el que se borrará la excepción no administrada actual.</span><span class="sxs-lookup"><span data-stu-id="57868-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57868-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="57868-107">Remarks</span></span>  
 <span data-ttu-id="57868-108">Llame a este método antes de llamar a [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) cuando un subproceso ha notificado una excepción no administrada que se debe omitir el depurador.</span><span class="sxs-lookup"><span data-stu-id="57868-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="57868-109">Esto borrará los eventos de fuera de banda (OOB) en el subproceso y pendientes en banda (IB).</span><span class="sxs-lookup"><span data-stu-id="57868-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="57868-110">Se borran automáticamente todos los puntos de interrupción OOB y excepciones de paso a paso.</span><span class="sxs-lookup"><span data-stu-id="57868-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="57868-111">Use [Icordebugthread2](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) interceptar actual excepción en un subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="57868-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57868-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57868-112">Requirements</span></span>  
 <span data-ttu-id="57868-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57868-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57868-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57868-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57868-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57868-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57868-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57868-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
