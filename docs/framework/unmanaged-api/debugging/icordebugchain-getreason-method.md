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
ms.openlocfilehash: 9d02a68e80e34be906e9fe09f3457a0f2214c6f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405072"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="73078-102">ICorDebugChain::GetReason (Método)</span><span class="sxs-lookup"><span data-stu-id="73078-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="73078-103">Obtiene la razón para la génesis de esta cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="73078-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73078-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73078-104">Syntax</span></span>  
  
```  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73078-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73078-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="73078-106">[out] Un puntero a un valor (una combinación bit a bit) de la enumeración CorDebugChainReason que indica la razón para la génesis de esta cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="73078-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73078-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73078-107">Requirements</span></span>  
 <span data-ttu-id="73078-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73078-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73078-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73078-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73078-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73078-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73078-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73078-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
