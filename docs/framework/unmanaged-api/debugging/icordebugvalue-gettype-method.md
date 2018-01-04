---
title: "ICorDebugValue::GetType (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue.GetType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a79ef332361fdaa3a23cc4e13daa8b4a8303d2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="b4b71-102">ICorDebugValue::GetType (Método)</span><span class="sxs-lookup"><span data-stu-id="b4b71-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="b4b71-103">Obtiene el tipo primitivo de este objeto de "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="b4b71-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4b71-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4b71-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4b71-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4b71-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="b4b71-106">[out] Un puntero a un valor de la enumeración "CorElementType" que indica el tipo del valor.</span><span class="sxs-lookup"><span data-stu-id="b4b71-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4b71-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b4b71-107">Remarks</span></span>  
 <span data-ttu-id="b4b71-108">Si el objeto es un tipo complejo de tiempo de ejecución, se puede examinar ese tipo a través de las subclases adecuadas de la `ICorDebugValue` interfaz.</span><span class="sxs-lookup"><span data-stu-id="b4b71-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="b4b71-109">Por ejemplo, "ICorDebugObjectValue", que se hereda de `ICorDebugValue`, representa un tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="b4b71-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="b4b71-110">El `GetType` y [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) cada uno de métodos devuelve información sobre el tipo de un valor.</span><span class="sxs-lookup"><span data-stu-id="b4b71-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="b4b71-111">Ambos son reemplazados por los con elementos genéricos [ICorDebugValue2:: GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b4b71-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4b71-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4b71-112">Requirements</span></span>  
 <span data-ttu-id="b4b71-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4b71-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4b71-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4b71-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4b71-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4b71-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4b71-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4b71-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b71-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4b71-117">See Also</span></span>  
 
