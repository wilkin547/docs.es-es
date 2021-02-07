---
description: 'Más información acerca de: ICorDebugObjectValue:: Isvalueclass ((método)'
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
ms.openlocfilehash: bf3ce94a06092209507fd1ff737e09a77b5d0c70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728930"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="d5cec-103">ICorDebugObjectValue::IsValueClass (Método)</span><span class="sxs-lookup"><span data-stu-id="d5cec-103">ICorDebugObjectValue::IsValueClass Method</span></span>

<span data-ttu-id="d5cec-104">Obtiene un valor que indica si este valor de objeto es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="d5cec-104">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5cec-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5cec-105">Syntax</span></span>  
  
```cpp  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5cec-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5cec-106">Parameters</span></span>  

 `pbIsValueClass`  
 <span data-ttu-id="d5cec-107">enuncia Un puntero a un valor booleano que es `true` si el valor del objeto, representado por este "ICorDebugObjectValue", es un tipo de valor en lugar de un tipo de referencia; de lo contrario, `pbIsValueClass` es `false` .</span><span class="sxs-lookup"><span data-stu-id="d5cec-107">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5cec-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5cec-108">Requirements</span></span>  

 <span data-ttu-id="d5cec-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5cec-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5cec-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5cec-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5cec-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5cec-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5cec-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5cec-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5cec-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5cec-113">See also</span></span>
