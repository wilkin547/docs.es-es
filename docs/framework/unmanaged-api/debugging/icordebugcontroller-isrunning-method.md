---
title: ICorDebugController::IsRunning (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.IsRunning
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::IsRunning
helpviewer_keywords:
- IsRunning method [.NET Framework debugging]
- ICorDebugController::IsRunning method [.NET Framework debugging]
ms.assetid: b33ff059-40c4-4dfe-9cb2-21bfed2de0b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5eae9e14bcd0ca430f03a873818246896438463
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749272"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="f1b4c-102">ICorDebugController::IsRunning (Método)</span><span class="sxs-lookup"><span data-stu-id="f1b4c-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="f1b4c-103">Obtiene un valor que indica si los subprocesos del proceso se están ejecutando libremente.</span><span class="sxs-lookup"><span data-stu-id="f1b4c-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1b4c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1b4c-104">Syntax</span></span>  
  
```  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1b4c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1b4c-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="f1b4c-106">[out] Un puntero a un valor que es `true` si se ejecutan los subprocesos del proceso libremente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="f1b4c-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1b4c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1b4c-107">Requirements</span></span>  
 <span data-ttu-id="f1b4c-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1b4c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1b4c-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1b4c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1b4c-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1b4c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1b4c-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1b4c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b4c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1b4c-112">See also</span></span>
