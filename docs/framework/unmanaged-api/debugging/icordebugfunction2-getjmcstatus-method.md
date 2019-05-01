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
ms.openlocfilehash: d23a0a489cfe13201b7798920feb3528db3b0709
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988668"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="f41af-102">ICorDebugFunction2::GetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="f41af-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="f41af-103">Obtiene un valor que indica si la función representada por este objeto ICorDebugFunction2 está marcada como código de usuario.</span><span class="sxs-lookup"><span data-stu-id="f41af-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f41af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f41af-104">Syntax</span></span>  
  
```  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f41af-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f41af-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="f41af-106">[out] Un puntero a un valor booleano que es `true`, si esta función está marcada como código de usuario; en caso contrario, el valor es `false`.</span><span class="sxs-lookup"><span data-stu-id="f41af-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f41af-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f41af-107">Remarks</span></span>  
 <span data-ttu-id="f41af-108">Si la función representada por este `ICorDebugFunction2` no se puede depurar, `pbIsJustMyCode` siempre será `false`.</span><span class="sxs-lookup"><span data-stu-id="f41af-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f41af-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f41af-109">Requirements</span></span>  
 <span data-ttu-id="f41af-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f41af-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f41af-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f41af-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f41af-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f41af-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f41af-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f41af-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
