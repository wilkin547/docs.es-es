---
title: ICorDebugThread::GetDebugState (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68df19120f2e0b45e73f9d5e137afc8a5e7ac513
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987160"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="5d2f2-102">ICorDebugThread::GetDebugState (Método)</span><span class="sxs-lookup"><span data-stu-id="5d2f2-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="5d2f2-103">Obtiene el estado de depuración actual de este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="5d2f2-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d2f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d2f2-104">Syntax</span></span>  
  
```  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d2f2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d2f2-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="5d2f2-106">[out] Un puntero a una combinación bit a bit de valores de enumeración CorDebugThreadState que describe el estado de depuración actual de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="5d2f2-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d2f2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d2f2-107">Remarks</span></span>  
 <span data-ttu-id="5d2f2-108">Si actualmente se detiene el proceso, `pState` representa el estado de depuración que existiría para este subproceso si el proceso se puede continuar, no el estado actual real de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="5d2f2-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d2f2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d2f2-109">Requirements</span></span>  
 <span data-ttu-id="5d2f2-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d2f2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d2f2-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d2f2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d2f2-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d2f2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d2f2-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d2f2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
