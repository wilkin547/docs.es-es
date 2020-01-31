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
ms.openlocfilehash: d15938e94d647fd5fded23c72bdc200d198d21a7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792705"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="b4f97-102">ICorDebugObjectValue::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="b4f97-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="b4f97-103">Obtiene la clase de este valor de objeto.</span><span class="sxs-lookup"><span data-stu-id="b4f97-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f97-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4f97-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4f97-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b4f97-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="b4f97-106">enuncia Puntero a la dirección de un objeto "ICorDebugClass" que representa la clase del valor del objeto representado por este objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="b4f97-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4f97-107">Notas</span><span class="sxs-lookup"><span data-stu-id="b4f97-107">Remarks</span></span>  
 <span data-ttu-id="b4f97-108">Los métodos `GetClass` e [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) devuelven información sobre el tipo de un valor. ambos se sustituyen por el [ICorDebugValue2:: GetExactType (](icordebugvalue2-getexacttype-method.md)compatible con genéricos.</span><span class="sxs-lookup"><span data-stu-id="b4f97-108">The `GetClass` and [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4f97-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b4f97-109">Requirements</span></span>  
 <span data-ttu-id="b4f97-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4f97-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4f97-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4f97-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4f97-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4f97-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4f97-113">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4f97-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f97-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4f97-114">See also</span></span>
