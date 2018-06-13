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
ms.openlocfilehash: 4605b893169ccfc592aae0d07dc032f455314cc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412738"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="fad2f-102">ICorDebugController::IsRunning (Método)</span><span class="sxs-lookup"><span data-stu-id="fad2f-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="fad2f-103">Obtiene un valor que indica si los subprocesos del proceso se están ejecutando libremente.</span><span class="sxs-lookup"><span data-stu-id="fad2f-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fad2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fad2f-104">Syntax</span></span>  
  
```  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fad2f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fad2f-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="fad2f-106">[out] Un puntero a un valor que es `true` si los subprocesos del proceso se están ejecutando libremente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="fad2f-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fad2f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fad2f-107">Requirements</span></span>  
 <span data-ttu-id="fad2f-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fad2f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fad2f-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fad2f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fad2f-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fad2f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fad2f-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fad2f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad2f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fad2f-112">See Also</span></span>  
 
