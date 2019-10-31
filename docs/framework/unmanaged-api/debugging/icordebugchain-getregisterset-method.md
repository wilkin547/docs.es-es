---
title: ICorDebugChain::GetRegisterSet (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetRegisterSet
helpviewer_keywords:
- ICorDebugChain::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: bc4288b6-3331-4ae3-990d-e1d6e62ecb67
topic_type:
- apiref
ms.openlocfilehash: d6ee36ac4d4510637e5f8240c3b8930a9bec7970
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123831"
---
# <a name="icordebugchaingetregisterset-method"></a><span data-ttu-id="d5f24-102">ICorDebugChain::GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="d5f24-102">ICorDebugChain::GetRegisterSet Method</span></span>
<span data-ttu-id="d5f24-103">Obtiene el conjunto de registros para la parte activa de esta cadena.</span><span class="sxs-lookup"><span data-stu-id="d5f24-103">Gets the register set for the active part of this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5f24-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5f24-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5f24-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5f24-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="d5f24-106">enuncia Puntero a la dirección de un objeto [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) que representa el conjunto de registros para la parte activa de esta cadena.</span><span class="sxs-lookup"><span data-stu-id="d5f24-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for the active part of this chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5f24-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5f24-107">Requirements</span></span>  
 <span data-ttu-id="d5f24-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5f24-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5f24-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5f24-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5f24-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5f24-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5f24-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5f24-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
