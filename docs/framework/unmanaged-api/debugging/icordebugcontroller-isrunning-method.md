---
description: 'Más información sobre: ICorDebugController:: IsRunning (método)'
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
ms.openlocfilehash: 6a0628cc39765d9cb295877d912d92dbb27937da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764585"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="75a88-103">ICorDebugController::IsRunning (Método)</span><span class="sxs-lookup"><span data-stu-id="75a88-103">ICorDebugController::IsRunning Method</span></span>

<span data-ttu-id="75a88-104">Obtiene un valor que indica si los subprocesos del proceso se están ejecutando libremente.</span><span class="sxs-lookup"><span data-stu-id="75a88-104">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75a88-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75a88-105">Syntax</span></span>  
  
```cpp  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75a88-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75a88-106">Parameters</span></span>  

 `pbRunning`  
 <span data-ttu-id="75a88-107">enuncia Un puntero a un valor que es `true` si los subprocesos del proceso se están ejecutando libremente; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="75a88-107">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75a88-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75a88-108">Requirements</span></span>  

 <span data-ttu-id="75a88-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75a88-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75a88-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75a88-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75a88-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75a88-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75a88-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75a88-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75a88-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="75a88-113">See also</span></span>
