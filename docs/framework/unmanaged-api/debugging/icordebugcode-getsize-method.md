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
ms.openlocfilehash: 3a9a43735ec80821c2380b824bfced99113cf08f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651102"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="73486-102">ICorDebugCode::GetSize (Método)</span><span class="sxs-lookup"><span data-stu-id="73486-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="73486-103">Obtiene el tamaño, en bytes, del código binario representado por "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="73486-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73486-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73486-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73486-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73486-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="73486-106">[out] Un puntero al tamaño, en bytes, del archivo binario del que este código `ICorDebugCode` objeto representa.</span><span class="sxs-lookup"><span data-stu-id="73486-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73486-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73486-107">Requirements</span></span>  
 <span data-ttu-id="73486-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73486-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73486-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73486-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73486-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73486-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73486-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73486-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73486-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="73486-112">See also</span></span>

