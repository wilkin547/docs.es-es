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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e6798c2574167ec1a013429b380d8fa6c878dad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416568"
---
# <a name="icordebugthread2getvolatileosthreadid-method"></a><span data-ttu-id="5c495-102">ICorDebugThread2::GetVolatileOSThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="5c495-102">ICorDebugThread2::GetVolatileOSThreadID Method</span></span>
<span data-ttu-id="5c495-103">Obtiene el identificador de subproceso del sistema operativo para esta instancia de ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="5c495-103">Gets the operating system thread identifier for this ICorDebugThread2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c495-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c495-104">Syntax</span></span>  
  
```  
HRESULT GetVolatileOSThreadID (  
    [out] DWORD    *pdwTid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c495-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c495-105">Parameters</span></span>  
 `pdwTid`  
 <span data-ttu-id="5c495-106">[out] El identificador de subproceso de sistema operativo para este subproceso.</span><span class="sxs-lookup"><span data-stu-id="5c495-106">[out] The operating system thread identifier for this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c495-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c495-107">Requirements</span></span>  
 <span data-ttu-id="5c495-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c495-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c495-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c495-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c495-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c495-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c495-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c495-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
