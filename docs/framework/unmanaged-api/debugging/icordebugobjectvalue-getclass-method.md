---
title: ICorDebugObjectValue::GetClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
ms.openlocfilehash: 42e5ffeeb81bc5e9a99c8ada8d58296fc9f610d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695418"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="934ff-102">ICorDebugObjectValue::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="934ff-102">ICorDebugObjectValue::GetClass Method</span></span>

<span data-ttu-id="934ff-103">Obtiene la clase de este valor de objeto.</span><span class="sxs-lookup"><span data-stu-id="934ff-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="934ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="934ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="934ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="934ff-105">Parameters</span></span>  

 `ppClass`  
 <span data-ttu-id="934ff-106">enuncia Puntero a la dirección de un objeto "ICorDebugClass" que representa la clase del valor del objeto representado por este objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="934ff-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="934ff-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="934ff-107">Remarks</span></span>  

 <span data-ttu-id="934ff-108">Los `GetClass` métodos y [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) devuelven información sobre el tipo de un valor; se sustituyen por el [ICorDebugValue2:: GetExactType (](icordebugvalue2-getexacttype-method.md)compatible con genéricos.</span><span class="sxs-lookup"><span data-stu-id="934ff-108">The `GetClass` and [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="934ff-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="934ff-109">Requirements</span></span>  

 <span data-ttu-id="934ff-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="934ff-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="934ff-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="934ff-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="934ff-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="934ff-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="934ff-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="934ff-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="934ff-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="934ff-114">See also</span></span>
