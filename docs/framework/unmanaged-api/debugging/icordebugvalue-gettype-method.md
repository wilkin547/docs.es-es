---
title: ICorDebugValue::GetType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 284a74823b01305f8c6e025f70bb9209c8607b7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137075"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="23206-102">ICorDebugValue::GetType (Método)</span><span class="sxs-lookup"><span data-stu-id="23206-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="23206-103">Obtiene el tipo primitivo de este objeto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="23206-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23206-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23206-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23206-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="23206-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="23206-106">enuncia Un puntero a un valor de la enumeración "CorElementType" que indica el tipo del valor.</span><span class="sxs-lookup"><span data-stu-id="23206-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23206-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23206-107">Remarks</span></span>  
 <span data-ttu-id="23206-108">Si el objeto es un tipo complejo en tiempo de ejecución, ese tipo se puede examinar en las subclases adecuadas de la interfaz `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="23206-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="23206-109">Por ejemplo, "ICorDebugObjectValue", que hereda de `ICorDebugValue`, representa un tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="23206-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="23206-110">Los métodos `GetType` e [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) devuelven información sobre el tipo de un valor.</span><span class="sxs-lookup"><span data-stu-id="23206-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="23206-111">Ambos se sustituyen por el método [ICorDebugValue2:: GetExactType (](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) compatible con genéricos.</span><span class="sxs-lookup"><span data-stu-id="23206-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23206-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23206-112">Requirements</span></span>  
 <span data-ttu-id="23206-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23206-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23206-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23206-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23206-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23206-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23206-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23206-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23206-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="23206-117">See also</span></span>
