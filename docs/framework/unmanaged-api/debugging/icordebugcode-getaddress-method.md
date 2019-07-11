---
title: ICorDebugCode::GetAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbdf8649e3cb2221e5c74eefd22959dc4b382236
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747686"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="bb68d-102">ICorDebugCode::GetAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="bb68d-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="bb68d-103">Obtiene la dirección virtual relativa (RVA) del segmento de código que representa esta interfaz "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="bb68d-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb68d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb68d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb68d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bb68d-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="bb68d-106">[out] Un puntero a la dirección RVA del segmento de código.</span><span class="sxs-lookup"><span data-stu-id="bb68d-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb68d-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb68d-107">Requirements</span></span>  
 <span data-ttu-id="bb68d-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb68d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb68d-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb68d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb68d-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb68d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb68d-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb68d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb68d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb68d-112">See also</span></span>
