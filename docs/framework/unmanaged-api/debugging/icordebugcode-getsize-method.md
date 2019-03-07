---
title: ICorDebugCode::GetSize (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bd21e43973d116e4383d88bd5ce90f0fbfeb1a6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471499"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="fd4b1-102">ICorDebugCode::GetSize (Método)</span><span class="sxs-lookup"><span data-stu-id="fd4b1-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="fd4b1-103">Obtiene el tamaño, en bytes, del código binario representado por "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="fd4b1-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd4b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd4b1-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd4b1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd4b1-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="fd4b1-106">[out] Un puntero al tamaño, en bytes, del archivo binario del que este código `ICorDebugCode` objeto representa.</span><span class="sxs-lookup"><span data-stu-id="fd4b1-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd4b1-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd4b1-107">Requirements</span></span>  
 <span data-ttu-id="fd4b1-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd4b1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd4b1-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd4b1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd4b1-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd4b1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd4b1-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd4b1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd4b1-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd4b1-112">See also</span></span>

