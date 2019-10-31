---
title: ICorDebugThread2::GetVolatileOSThreadID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetVolatileOSThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetVolatileOSThreadID
helpviewer_keywords:
- GetVolatileOSThreadID method [.NET Framework debugging]
- ICorDebugThread2::GetVolatileOSThreadID method [.NET Framework debugging]
ms.assetid: f0922545-c2cf-40c8-9ef6-ca033563e682
topic_type:
- apiref
ms.openlocfilehash: 2e49dd95cf5d78c0a0f4fa075126eca19dea2693
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138718"
---
# <a name="icordebugthread2getvolatileosthreadid-method"></a><span data-ttu-id="d16ac-102">ICorDebugThread2::GetVolatileOSThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="d16ac-102">ICorDebugThread2::GetVolatileOSThreadID Method</span></span>
<span data-ttu-id="d16ac-103">Obtiene el identificador del subproceso del sistema operativo para este ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="d16ac-103">Gets the operating system thread identifier for this ICorDebugThread2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d16ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d16ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVolatileOSThreadID (  
    [out] DWORD    *pdwTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d16ac-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d16ac-105">Parameters</span></span>  
 `pdwTid`  
 <span data-ttu-id="d16ac-106">enuncia Identificador del subproceso del sistema operativo para este subproceso.</span><span class="sxs-lookup"><span data-stu-id="d16ac-106">[out] The operating system thread identifier for this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d16ac-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d16ac-107">Requirements</span></span>  
 <span data-ttu-id="d16ac-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d16ac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d16ac-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d16ac-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d16ac-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d16ac-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d16ac-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d16ac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
