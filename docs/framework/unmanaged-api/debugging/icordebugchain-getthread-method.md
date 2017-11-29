---
title: "ICorDebugChain::GetThread (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1e8307134bc81041efe2a596131b5d309220a873
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="bc70b-102">ICorDebugChain::GetThread (Método)</span><span class="sxs-lookup"><span data-stu-id="bc70b-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="bc70b-103">Obtiene el subproceso físico que esta cadena de llamada es parte de.</span><span class="sxs-lookup"><span data-stu-id="bc70b-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc70b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc70b-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc70b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc70b-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="bc70b-106">[out] Un puntero a un objeto ICorDebugThread que representa el subproceso físico esta cadena de llamadas es parte de.</span><span class="sxs-lookup"><span data-stu-id="bc70b-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc70b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc70b-107">Requirements</span></span>  
 <span data-ttu-id="bc70b-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc70b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc70b-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc70b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc70b-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc70b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc70b-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc70b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
