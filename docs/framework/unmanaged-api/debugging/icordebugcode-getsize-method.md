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
ms.openlocfilehash: 678b7fbd595b1238b7025c22b0ed80b02ed4becd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085680"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="242af-102">ICorDebugCode::GetSize (Método)</span><span class="sxs-lookup"><span data-stu-id="242af-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="242af-103">Obtiene el tamaño, en bytes, del código binario representado por "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="242af-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="242af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="242af-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="242af-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="242af-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="242af-106">[out] Un puntero al tamaño, en bytes, del archivo binario del que este código `ICorDebugCode` objeto representa.</span><span class="sxs-lookup"><span data-stu-id="242af-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="242af-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="242af-107">Requirements</span></span>  
 <span data-ttu-id="242af-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="242af-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="242af-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="242af-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="242af-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="242af-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="242af-111">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="242af-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="242af-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="242af-112">See also</span></span>
