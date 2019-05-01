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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f366a40e1e3cd196f480c5849c49419c7daeea9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989487"
---
# <a name="icordebugchaingetregisterset-method"></a><span data-ttu-id="273f0-102">ICorDebugChain::GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="273f0-102">ICorDebugChain::GetRegisterSet Method</span></span>
<span data-ttu-id="273f0-103">Obtiene el conjunto de registros para la parte activa de esta cadena.</span><span class="sxs-lookup"><span data-stu-id="273f0-103">Gets the register set for the active part of this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="273f0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="273f0-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="273f0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="273f0-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="273f0-106">[out] Un puntero a la dirección de un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) establece el objeto que representa el registro para la parte activa de esta cadena.</span><span class="sxs-lookup"><span data-stu-id="273f0-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for the active part of this chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="273f0-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="273f0-107">Requirements</span></span>  
 <span data-ttu-id="273f0-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="273f0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="273f0-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="273f0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="273f0-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="273f0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="273f0-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="273f0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
