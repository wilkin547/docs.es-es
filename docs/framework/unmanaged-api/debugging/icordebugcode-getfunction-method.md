---
title: ICorDebugCode::GetFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0104a52c3aa206f86daff30d9d16298e6beae324
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750253"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="db03d-102">ICorDebugCode::GetFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="db03d-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="db03d-103">Obtiene la "ICorDebugFunction" asociado "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="db03d-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db03d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db03d-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db03d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db03d-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="db03d-106">[out] Un puntero a la dirección de la función.</span><span class="sxs-lookup"><span data-stu-id="db03d-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db03d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db03d-107">Remarks</span></span>  
 <span data-ttu-id="db03d-108">`ICorDebugCode` y `ICorDebugFunction` mantienen una relación uno a uno.</span><span class="sxs-lookup"><span data-stu-id="db03d-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db03d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db03d-109">Requirements</span></span>  
 <span data-ttu-id="db03d-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db03d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db03d-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db03d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db03d-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db03d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db03d-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db03d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db03d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="db03d-114">See also</span></span>
