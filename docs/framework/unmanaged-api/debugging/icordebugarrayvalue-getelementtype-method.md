---
title: "ICorDebugArrayValue::GetElementType (Método)"
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
- ICorDebugArrayValue.GetElementType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementType
helpviewer_keywords:
- ICorDebugArrayValue::GetElementType method [.NET Framework debugging]
- GetElementType method [.NET Framework debugging]
ms.assetid: ed71961e-ae9b-4dfc-9554-06637696d697
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 17c1d51c01614a25d52f90557bb10b6842419995
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugarrayvaluegetelementtype-method"></a><span data-ttu-id="72519-102">ICorDebugArrayValue::GetElementType (Método)</span><span class="sxs-lookup"><span data-stu-id="72519-102">ICorDebugArrayValue::GetElementType Method</span></span>
<span data-ttu-id="72519-103">Obtiene un valor que indica el tipo simple de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="72519-103">Gets a value that indicates the simple type of the elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72519-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72519-104">Syntax</span></span>  
  
```  
HRESULT GetElementType (  
    [out] CorElementType  *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72519-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72519-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="72519-106">[out] Un puntero a un valor de la enumeración CorElementType que indica el tipo.</span><span class="sxs-lookup"><span data-stu-id="72519-106">[out] A pointer to a value of the CorElementType enumeration that indicates the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72519-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72519-107">Requirements</span></span>  
 <span data-ttu-id="72519-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72519-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72519-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72519-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72519-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72519-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72519-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72519-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
