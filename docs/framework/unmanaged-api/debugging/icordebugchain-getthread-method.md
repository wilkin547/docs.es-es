---
title: ICorDebugChain::GetThread (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d05002ecdb903a1adfeea88930083ba472164324
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745639"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="8a40c-102">ICorDebugChain::GetThread (Método)</span><span class="sxs-lookup"><span data-stu-id="8a40c-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="8a40c-103">Obtiene el subproceso físico que esta cadena de llamada es parte de.</span><span class="sxs-lookup"><span data-stu-id="8a40c-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a40c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a40c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a40c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a40c-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="8a40c-106">[out] Un puntero a un objeto ICorDebugThread que representa el subproceso físico esta cadena de llamada es parte de.</span><span class="sxs-lookup"><span data-stu-id="8a40c-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a40c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a40c-107">Requirements</span></span>  
 <span data-ttu-id="8a40c-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a40c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a40c-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a40c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a40c-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a40c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a40c-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a40c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
