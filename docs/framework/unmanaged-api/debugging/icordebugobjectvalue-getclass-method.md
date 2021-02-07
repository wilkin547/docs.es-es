---
description: 'Más información acerca de: ICorDebugObjectValue:: GetClass (método)'
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
ms.openlocfilehash: 4ea6a47814777da934aa14bba947a047c075396c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722222"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="0ee1c-103">ICorDebugObjectValue::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="0ee1c-103">ICorDebugObjectValue::GetClass Method</span></span>

<span data-ttu-id="0ee1c-104">Obtiene la clase de este valor de objeto.</span><span class="sxs-lookup"><span data-stu-id="0ee1c-104">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ee1c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ee1c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ee1c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0ee1c-106">Parameters</span></span>  

 `ppClass`  
 <span data-ttu-id="0ee1c-107">enuncia Puntero a la dirección de un objeto "ICorDebugClass" que representa la clase del valor del objeto representado por este objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="0ee1c-107">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ee1c-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0ee1c-108">Remarks</span></span>  

 <span data-ttu-id="0ee1c-109">Los `GetClass` métodos y [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) devuelven información sobre el tipo de un valor; se sustituyen por el [ICorDebugValue2:: GetExactType (](icordebugvalue2-getexacttype-method.md)compatible con genéricos.</span><span class="sxs-lookup"><span data-stu-id="0ee1c-109">The `GetClass` and [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ee1c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ee1c-110">Requirements</span></span>  

 <span data-ttu-id="0ee1c-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ee1c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ee1c-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ee1c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ee1c-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ee1c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ee1c-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ee1c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee1c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ee1c-115">See also</span></span>
