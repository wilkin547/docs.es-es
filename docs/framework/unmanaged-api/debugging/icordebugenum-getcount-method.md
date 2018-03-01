---
title: "ICorDebugEnum::GetCount (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::GetCount
helpviewer_keywords:
- ICorDebugEnum::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: d8a74304-1cb2-4977-a21d-e1af48c563ff
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b2be2e198007e15a0bae3ba0d3dd0cf1cf9983c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="dc07a-102">ICorDebugEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="dc07a-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="dc07a-103">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="dc07a-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc07a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc07a-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dc07a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc07a-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="dc07a-106">[out] Un puntero al número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="dc07a-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc07a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc07a-107">Requirements</span></span>  
 <span data-ttu-id="dc07a-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc07a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc07a-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc07a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc07a-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc07a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc07a-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc07a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
