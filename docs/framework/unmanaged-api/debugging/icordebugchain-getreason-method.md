---
description: 'Más información sobre: ICorDebugChain:: GetReason ((método)'
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
ms.openlocfilehash: 0952d09db6d43f7970ba9e8c46c409fb2cd4b131
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694974"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="d4051-103">ICorDebugChain::GetReason (Método)</span><span class="sxs-lookup"><span data-stu-id="d4051-103">ICorDebugChain::GetReason Method</span></span>

<span data-ttu-id="d4051-104">Obtiene el motivo del Genesis de esta cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="d4051-104">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4051-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4051-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4051-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4051-106">Parameters</span></span>  

 `pReason`  
 <span data-ttu-id="d4051-107">enuncia Un puntero a un valor (una combinación bit a bit) de la enumeración CorDebugChainReason (que indica el motivo de la Genesis de esta cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="d4051-107">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4051-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4051-108">Requirements</span></span>  

 <span data-ttu-id="d4051-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4051-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4051-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4051-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4051-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4051-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4051-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4051-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
