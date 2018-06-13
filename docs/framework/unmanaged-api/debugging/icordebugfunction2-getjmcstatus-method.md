---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acf0ba3938568524479e12b93ae8cebbcf52f909
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411734"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="e782e-102">ICorDebugFunction2::GetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="e782e-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="e782e-103">Obtiene un valor que indica si la función representada por este objeto ICorDebugFunction2 está marcada como código de usuario.</span><span class="sxs-lookup"><span data-stu-id="e782e-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e782e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e782e-104">Syntax</span></span>  
  
```  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e782e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e782e-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="e782e-106">[out] Un puntero a un valor booleano que es `true`, si esta función está marcada como código de usuario; en caso contrario, el valor es `false`.</span><span class="sxs-lookup"><span data-stu-id="e782e-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e782e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e782e-107">Remarks</span></span>  
 <span data-ttu-id="e782e-108">Si la función representada por este `ICorDebugFunction2` no se pueden depurar, `pbIsJustMyCode` siempre será `false`.</span><span class="sxs-lookup"><span data-stu-id="e782e-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e782e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e782e-109">Requirements</span></span>  
 <span data-ttu-id="e782e-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e782e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e782e-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e782e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e782e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e782e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e782e-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e782e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
