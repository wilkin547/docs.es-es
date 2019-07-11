---
title: ICorDebugChain::GetPrevious (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetPrevious
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31c795c2fbbfdc45b6e1aac6684f730f55fc106a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746419"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="3ec9d-102">ICorDebugChain::GetPrevious (Método)</span><span class="sxs-lookup"><span data-stu-id="3ec9d-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="3ec9d-103">Obtiene la cadena anterior de marcos del subproceso.</span><span class="sxs-lookup"><span data-stu-id="3ec9d-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ec9d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ec9d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ec9d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3ec9d-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="3ec9d-106">[out] Un puntero a la dirección de un objeto ICorDebugChain que representa la cadena anterior de marcos para este subproceso.</span><span class="sxs-lookup"><span data-stu-id="3ec9d-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="3ec9d-107">Si esta cadena es la primera cadena, `ppChain` es null.</span><span class="sxs-lookup"><span data-stu-id="3ec9d-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ec9d-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ec9d-108">Requirements</span></span>  
 <span data-ttu-id="3ec9d-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ec9d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ec9d-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ec9d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ec9d-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ec9d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ec9d-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ec9d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
