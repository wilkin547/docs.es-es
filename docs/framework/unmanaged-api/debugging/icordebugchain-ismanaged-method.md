---
title: ICorDebugChain::IsManaged (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c8c61cc12e438c0786b6e093b8bb1ea288a42e3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401172"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="a64bc-102">ICorDebugChain::IsManaged (Método)</span><span class="sxs-lookup"><span data-stu-id="a64bc-102">ICorDebugChain::IsManaged Method</span></span>
<span data-ttu-id="a64bc-103">Obtiene un valor que indica si esta cadena ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="a64bc-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a64bc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a64bc-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a64bc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a64bc-105">Parameters</span></span>  
 `pManaged`  
 <span data-ttu-id="a64bc-106">[out] `true` si esta cadena ejecuta código administrado; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a64bc-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a64bc-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a64bc-107">Requirements</span></span>  
 <span data-ttu-id="a64bc-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a64bc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a64bc-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a64bc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a64bc-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a64bc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a64bc-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a64bc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
