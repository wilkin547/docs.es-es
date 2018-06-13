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
ms.openlocfilehash: dff7a42cac7002e170e8da3c3505fe37bd5eb85f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418768"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="afb17-102">ICorDebugObjectValue::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="afb17-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="afb17-103">Obtiene la clase de valor de este objeto.</span><span class="sxs-lookup"><span data-stu-id="afb17-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afb17-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="afb17-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="afb17-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="afb17-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="afb17-106">[out] Un puntero a la dirección de un objeto de "ICorDebugClass" que representa la clase del valor del objeto representado por este objeto de "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="afb17-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afb17-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="afb17-107">Remarks</span></span>  
 <span data-ttu-id="afb17-108">El `GetClass` y [ICorDebugValue:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) cada uno de métodos devuelve información sobre el tipo de un valor; ambos son reemplazados por los con elementos genéricos [ICorDebugValue2:: GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="afb17-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afb17-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="afb17-109">Requirements</span></span>  
 <span data-ttu-id="afb17-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afb17-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afb17-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afb17-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afb17-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afb17-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afb17-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afb17-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb17-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="afb17-114">See Also</span></span>  
    
 
