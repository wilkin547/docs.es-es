---
title: ICorDebugObjectValue::IsValueClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
ms.openlocfilehash: 13b100012215a7c2cee51ad5af39ec1447ab4e5b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207514"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="b7ade-102">ICorDebugObjectValue::IsValueClass (Método)</span><span class="sxs-lookup"><span data-stu-id="b7ade-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="b7ade-103">Obtiene un valor que indica si este valor de objeto es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="b7ade-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7ade-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7ade-104">Syntax</span></span>  
  
```cpp  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7ade-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7ade-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="b7ade-106">enuncia Un puntero a un valor booleano que es `true` si el valor del objeto, representado por este "ICorDebugObjectValue", es un tipo de valor en lugar de un tipo de referencia; de lo contrario, `pbIsValueClass` es `false` .</span><span class="sxs-lookup"><span data-stu-id="b7ade-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7ade-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7ade-107">Requirements</span></span>  
 <span data-ttu-id="b7ade-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7ade-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7ade-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7ade-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7ade-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7ade-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7ade-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7ade-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7ade-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7ade-112">See also</span></span>
