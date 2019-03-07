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
ms.openlocfilehash: 7eef04dfb305978c81f465ecb37eda75a52f25e4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502961"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="db1b3-102">ICorDebugController::IsRunning (Método)</span><span class="sxs-lookup"><span data-stu-id="db1b3-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="db1b3-103">Obtiene un valor que indica si los subprocesos del proceso se están ejecutando libremente.</span><span class="sxs-lookup"><span data-stu-id="db1b3-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db1b3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db1b3-104">Syntax</span></span>  
  
```  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db1b3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db1b3-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="db1b3-106">[out] Un puntero a un valor que es `true` si se ejecutan los subprocesos del proceso libremente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="db1b3-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db1b3-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db1b3-107">Requirements</span></span>  
 <span data-ttu-id="db1b3-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db1b3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db1b3-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db1b3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db1b3-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db1b3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db1b3-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db1b3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db1b3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="db1b3-112">See also</span></span>

