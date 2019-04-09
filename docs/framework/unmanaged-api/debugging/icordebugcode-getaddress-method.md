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
ms.openlocfilehash: 11ced90b88f083eb69b06d197d64a8ef4252f9d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141503"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="8ddcb-102">ICorDebugCode::GetAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="8ddcb-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="8ddcb-103">Obtiene la dirección virtual relativa (RVA) del segmento de código que representa esta interfaz "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="8ddcb-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ddcb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ddcb-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ddcb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8ddcb-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="8ddcb-106">[out] Un puntero a la dirección RVA del segmento de código.</span><span class="sxs-lookup"><span data-stu-id="8ddcb-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ddcb-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ddcb-107">Requirements</span></span>  
 <span data-ttu-id="8ddcb-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ddcb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ddcb-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ddcb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ddcb-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ddcb-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8ddcb-111">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8ddcb-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8ddcb-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ddcb-112">See also</span></span>
