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
ms.openlocfilehash: 94672c88864efc431acde8f29e406f4fbbc644ee
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894546"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="b0505-102">ICorDebugChain::GetReason (Método)</span><span class="sxs-lookup"><span data-stu-id="b0505-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="b0505-103">Obtiene el motivo del Genesis de esta cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="b0505-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0505-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0505-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0505-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b0505-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="b0505-106">enuncia Un puntero a un valor (una combinación bit a bit) de la enumeración CorDebugChainReason (que indica el motivo de la Genesis de esta cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="b0505-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0505-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0505-107">Requirements</span></span>  
 <span data-ttu-id="b0505-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0505-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0505-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0505-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0505-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0505-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0505-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0505-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
