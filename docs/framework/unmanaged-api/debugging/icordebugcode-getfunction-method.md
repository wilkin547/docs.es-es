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
ms.openlocfilehash: 8d0e7f20be3f18e49dcc1b986460d5da0c3d7777
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401945"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="15208-102">ICorDebugCode::GetFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="15208-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="15208-103">Obtiene la "ICorDebugFunction" asociado "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="15208-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15208-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15208-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15208-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15208-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="15208-106">[out] Un puntero a la dirección de la función.</span><span class="sxs-lookup"><span data-stu-id="15208-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15208-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15208-107">Remarks</span></span>  
 <span data-ttu-id="15208-108">`ICorDebugCode` y `ICorDebugFunction` mantienen una relación uno a uno.</span><span class="sxs-lookup"><span data-stu-id="15208-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15208-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15208-109">Requirements</span></span>  
 <span data-ttu-id="15208-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15208-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15208-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15208-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15208-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15208-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15208-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15208-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15208-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="15208-114">See Also</span></span>  
 
