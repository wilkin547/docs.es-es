---
description: 'Más información acerca de: ICorDebugFunction2:: GetJMCStatus ((método)'
title: ICorDebugFunction2::GetJMCStatus (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 42c72256df57b96a52737f4a0e5e90d6ba5d4e0c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692295"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="6e2b3-103">ICorDebugFunction2::GetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="6e2b3-103">ICorDebugFunction2::GetJMCStatus Method</span></span>

<span data-ttu-id="6e2b3-104">Obtiene un valor que indica si la función representada por este objeto ICorDebugFunction2 está marcada como código de usuario.</span><span class="sxs-lookup"><span data-stu-id="6e2b3-104">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e2b3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e2b3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e2b3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6e2b3-106">Parameters</span></span>  

 `pbIsJustMyCode`  
 <span data-ttu-id="6e2b3-107">enuncia Un puntero a un valor booleano que es `true` si esta función está marcada como código de usuario; de lo contrario, el valor es `false` .</span><span class="sxs-lookup"><span data-stu-id="6e2b3-107">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e2b3-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6e2b3-108">Remarks</span></span>  

 <span data-ttu-id="6e2b3-109">Si la función representada por este `ICorDebugFunction2` no se puede depurar, `pbIsJustMyCode` siempre será `false` .</span><span class="sxs-lookup"><span data-stu-id="6e2b3-109">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e2b3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6e2b3-110">Requirements</span></span>  

 <span data-ttu-id="6e2b3-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e2b3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e2b3-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e2b3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e2b3-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e2b3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e2b3-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e2b3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
