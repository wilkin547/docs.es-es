---
title: ICorDebugChain::GetReason (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- GetReason
helpviewer_keywords:
- GetReason method [.NET Framework debugging]
- ICorDebugChain::GetReason method [.NET Framework debugging]
ms.assetid: 9f9f62b9-113a-4a98-8f9b-b593cef27b03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48650a370f7d15724e20850e9d3b47dc8215f960
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498359"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="e9b05-102">ICorDebugChain::GetReason (Método)</span><span class="sxs-lookup"><span data-stu-id="e9b05-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="e9b05-103">Obtiene la razón para la génesis de esta cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="e9b05-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9b05-104">Syntax</span></span>  
  
```  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9b05-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9b05-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="e9b05-106">[out] Un puntero a un valor (una combinación bit a bit) de la enumeración CorDebugChainReason que indica la razón para la génesis de esta cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="e9b05-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9b05-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9b05-107">Requirements</span></span>  
 <span data-ttu-id="e9b05-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9b05-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9b05-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9b05-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9b05-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9b05-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9b05-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9b05-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
