---
title: "ICorDebugHeapValue::IsValid (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue.IsValid
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df7105c94a6f88c9c196f1d9d6be6f4a62f7c258
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="5eb3b-102">ICorDebugHeapValue::IsValid (Método)</span><span class="sxs-lookup"><span data-stu-id="5eb3b-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="5eb3b-103">Obtiene un valor que indica si el objeto representado por este ICorDebugHeapValue es válido.</span><span class="sxs-lookup"><span data-stu-id="5eb3b-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="5eb3b-104">Este método está en desuso en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5eb3b-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eb3b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5eb3b-105">Syntax</span></span>  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5eb3b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5eb3b-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="5eb3b-107">[out] Un puntero a un valor booleano que indica si este valor en el montón es válido.</span><span class="sxs-lookup"><span data-stu-id="5eb3b-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5eb3b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5eb3b-108">Remarks</span></span>  
 <span data-ttu-id="5eb3b-109">El valor no es válido si se ha recuperado por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5eb3b-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="5eb3b-110">Este método está en desuso.</span><span class="sxs-lookup"><span data-stu-id="5eb3b-110">This method has been deprecated.</span></span> <span data-ttu-id="5eb3b-111">En la versión 2.0 de .NET Framework, todos los valores son válidos hasta [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) se llama, en cuyo momento se invalidan los los valores.</span><span class="sxs-lookup"><span data-stu-id="5eb3b-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5eb3b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5eb3b-112">Requirements</span></span>  
 <span data-ttu-id="5eb3b-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5eb3b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eb3b-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5eb3b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5eb3b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5eb3b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5eb3b-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5eb3b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
