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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06e9c7af1c4a769bfb45a8e9f805d97b3bad94aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174192"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="e66a1-102">ICorDebugObjectValue::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="e66a1-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="e66a1-103">Obtiene la clase de valor de este objeto.</span><span class="sxs-lookup"><span data-stu-id="e66a1-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e66a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e66a1-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e66a1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e66a1-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="e66a1-106">[out] Un puntero a la dirección de un objeto "ICorDebugClass" que representa la clase del valor del objeto representado por este objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="e66a1-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e66a1-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e66a1-107">Remarks</span></span>  
 <span data-ttu-id="e66a1-108">El `GetClass` y [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) métodos cada devuelven información sobre el tipo de valor; ambos son reemplazados por los con elementos genéricos [Icordebugvalue2](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="e66a1-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e66a1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e66a1-109">Requirements</span></span>  
 <span data-ttu-id="e66a1-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e66a1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e66a1-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e66a1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e66a1-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e66a1-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e66a1-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e66a1-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e66a1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e66a1-114">See also</span></span>
