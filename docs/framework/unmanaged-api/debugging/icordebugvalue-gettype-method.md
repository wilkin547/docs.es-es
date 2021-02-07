---
description: 'Más información acerca de: ICorDebugValue:: GetType (método)'
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
ms.openlocfilehash: 750e73634683a03e811d2756cc62c16b6dcea3de
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690332"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="bf236-103">ICorDebugValue::GetType (Método)</span><span class="sxs-lookup"><span data-stu-id="bf236-103">ICorDebugValue::GetType Method</span></span>

<span data-ttu-id="bf236-104">Obtiene el tipo primitivo de este objeto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="bf236-104">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf236-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf236-105">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf236-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf236-106">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="bf236-107">enuncia Un puntero a un valor de la enumeración "CorElementType" que indica el tipo del valor.</span><span class="sxs-lookup"><span data-stu-id="bf236-107">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf236-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bf236-108">Remarks</span></span>  

 <span data-ttu-id="bf236-109">Si el objeto es un tipo complejo en tiempo de ejecución, ese tipo se puede examinar en las subclases adecuadas de la `ICorDebugValue` interfaz.</span><span class="sxs-lookup"><span data-stu-id="bf236-109">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="bf236-110">Por ejemplo, "ICorDebugObjectValue", que hereda de `ICorDebugValue` , representa un tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="bf236-110">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="bf236-111">Los `GetType` métodos y [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) devuelven información sobre el tipo de un valor.</span><span class="sxs-lookup"><span data-stu-id="bf236-111">The `GetType` and [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="bf236-112">Ambos se sustituyen por el método [ICorDebugValue2:: GetExactType (](icordebugvalue2-getexacttype-method.md) compatible con genéricos.</span><span class="sxs-lookup"><span data-stu-id="bf236-112">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf236-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf236-113">Requirements</span></span>  

 <span data-ttu-id="bf236-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf236-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf236-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf236-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf236-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf236-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf236-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf236-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf236-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf236-118">See also</span></span>
