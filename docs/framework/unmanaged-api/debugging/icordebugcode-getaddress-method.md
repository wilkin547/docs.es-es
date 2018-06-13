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
ms.openlocfilehash: e2de22729fd3d7a511c1105ebf810d0402bd73a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402088"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="9fe8e-102">ICorDebugCode::GetAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="9fe8e-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="9fe8e-103">Obtiene la dirección virtual relativa (RVA) del segmento de código que representa esta interfaz "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="9fe8e-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fe8e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fe8e-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9fe8e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9fe8e-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="9fe8e-106">[out] Un puntero a la RVA del segmento de código.</span><span class="sxs-lookup"><span data-stu-id="9fe8e-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fe8e-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9fe8e-107">Requirements</span></span>  
 <span data-ttu-id="9fe8e-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fe8e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fe8e-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fe8e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fe8e-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fe8e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fe8e-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fe8e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe8e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fe8e-112">See Also</span></span>  
 
