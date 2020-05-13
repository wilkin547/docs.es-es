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
ms.openlocfilehash: b0e8fd162ccc1cfc944fb870f493febfe2e5ef42
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207677"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="b59f4-102">ICorDebugObjectValue::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="b59f4-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="b59f4-103">Obtiene la clase de este valor de objeto.</span><span class="sxs-lookup"><span data-stu-id="b59f4-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b59f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b59f4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b59f4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b59f4-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="b59f4-106">enuncia Puntero a la dirección de un objeto "ICorDebugClass" que representa la clase del valor del objeto representado por este objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="b59f4-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b59f4-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b59f4-107">Remarks</span></span>  
 <span data-ttu-id="b59f4-108">Los `GetClass` métodos y [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) devuelven información sobre el tipo de un valor; se sustituyen por el [ICorDebugValue2:: GetExactType (](icordebugvalue2-getexacttype-method.md)compatible con genéricos.</span><span class="sxs-lookup"><span data-stu-id="b59f4-108">The `GetClass` and [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b59f4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b59f4-109">Requirements</span></span>  
 <span data-ttu-id="b59f4-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b59f4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b59f4-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b59f4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b59f4-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b59f4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b59f4-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b59f4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b59f4-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b59f4-114">See also</span></span>
