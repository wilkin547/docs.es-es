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
ms.openlocfilehash: 13125f60f596cb8a80d9c42c51a979f632de494b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379758"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="c1bfb-102">ICorDebugThread::GetDebugState (Método)</span><span class="sxs-lookup"><span data-stu-id="c1bfb-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="c1bfb-103">Obtiene el estado de depuración actual de este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="c1bfb-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1bfb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1bfb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1bfb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1bfb-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="c1bfb-106">enuncia Un puntero a una combinación bit a bit de valores de enumeración de CorDebugThreadState (que describe el estado de depuración actual de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="c1bfb-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1bfb-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c1bfb-107">Remarks</span></span>  
 <span data-ttu-id="c1bfb-108">Si el proceso está detenido actualmente, `pState` representa el estado de depuración que existirá para este subproceso si el proceso tuviera que continuar, no el estado actual real de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="c1bfb-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1bfb-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1bfb-109">Requirements</span></span>  
 <span data-ttu-id="c1bfb-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1bfb-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1bfb-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1bfb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1bfb-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1bfb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1bfb-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1bfb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
