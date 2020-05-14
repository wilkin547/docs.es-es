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
ms.openlocfilehash: a3cd62384ad87d072cd715d23d0e9ee9dac23270
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396743"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="746ba-102">ICorDebugValue::GetType (Método)</span><span class="sxs-lookup"><span data-stu-id="746ba-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="746ba-103">Obtiene el tipo primitivo de este objeto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="746ba-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="746ba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="746ba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="746ba-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="746ba-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="746ba-106">enuncia Un puntero a un valor de la enumeración "CorElementType" que indica el tipo del valor.</span><span class="sxs-lookup"><span data-stu-id="746ba-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="746ba-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="746ba-107">Remarks</span></span>  
 <span data-ttu-id="746ba-108">Si el objeto es un tipo complejo en tiempo de ejecución, ese tipo se puede examinar en las subclases adecuadas de la `ICorDebugValue` interfaz.</span><span class="sxs-lookup"><span data-stu-id="746ba-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="746ba-109">Por ejemplo, "ICorDebugObjectValue", que hereda de `ICorDebugValue` , representa un tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="746ba-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="746ba-110">Los `GetType` métodos y [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) devuelven información sobre el tipo de un valor.</span><span class="sxs-lookup"><span data-stu-id="746ba-110">The `GetType` and [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="746ba-111">Ambos se sustituyen por el método [ICorDebugValue2:: GetExactType (](icordebugvalue2-getexacttype-method.md) compatible con genéricos.</span><span class="sxs-lookup"><span data-stu-id="746ba-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="746ba-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="746ba-112">Requirements</span></span>  
 <span data-ttu-id="746ba-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="746ba-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="746ba-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="746ba-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="746ba-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="746ba-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="746ba-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="746ba-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="746ba-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="746ba-117">See also</span></span>
