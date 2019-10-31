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
ms.openlocfilehash: f054f8f2bd7c322e722a1e17290ba6fbad9e37b0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133518"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="6cc59-102">ICorDebugThread::GetDebugState (Método)</span><span class="sxs-lookup"><span data-stu-id="6cc59-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="6cc59-103">Obtiene el estado de depuración actual de este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="6cc59-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cc59-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6cc59-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cc59-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6cc59-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="6cc59-106">enuncia Un puntero a una combinación bit a bit de valores de enumeración de CorDebugThreadState (que describe el estado de depuración actual de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="6cc59-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6cc59-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6cc59-107">Remarks</span></span>  
 <span data-ttu-id="6cc59-108">Si el proceso está detenido actualmente, `pState` representa el estado de depuración que existirá para este subproceso si el proceso tuviera que continuar, no el estado actual real de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="6cc59-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cc59-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6cc59-109">Requirements</span></span>  
 <span data-ttu-id="6cc59-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6cc59-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cc59-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6cc59-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6cc59-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6cc59-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6cc59-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cc59-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
