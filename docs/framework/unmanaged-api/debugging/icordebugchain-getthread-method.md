---
description: 'Más información sobre: ICorDebugChain:: GetThread ((método)'
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
ms.openlocfilehash: 090cb40c3681792ce4a30cd342e65dc02ac3f381
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694929"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="efef2-103">ICorDebugChain::GetThread (Método)</span><span class="sxs-lookup"><span data-stu-id="efef2-103">ICorDebugChain::GetThread Method</span></span>

<span data-ttu-id="efef2-104">Obtiene el subproceso físico del que forma parte esta cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="efef2-104">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efef2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efef2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efef2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="efef2-106">Parameters</span></span>  

 `ppThread`  
 <span data-ttu-id="efef2-107">enuncia Un puntero a un objeto ICorDebugThread que representa el subproceso físico del que forma parte esta cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="efef2-107">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efef2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="efef2-108">Requirements</span></span>  

 <span data-ttu-id="efef2-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efef2-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efef2-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efef2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efef2-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efef2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efef2-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efef2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
