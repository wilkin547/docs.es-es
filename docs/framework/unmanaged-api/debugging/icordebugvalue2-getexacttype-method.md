---
title: ICorDebugValue2::GetExactType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1f8292a6964a6b25e228fcd07ab21a7ee5f5a04
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423337"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="630a0-102">ICorDebugValue2::GetExactType (Método)</span><span class="sxs-lookup"><span data-stu-id="630a0-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="630a0-103">Obtiene un puntero de interfaz a un objeto de "ICorDebugType" que representa el <xref:System.Type> de este valor.</span><span class="sxs-lookup"><span data-stu-id="630a0-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="630a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="630a0-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="630a0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="630a0-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="630a0-106">[out] Un puntero a la dirección de un `ICorDebugType` objeto que representa el <xref:System.Type> del valor representado por este objeto de "ICorDebugValue2".</span><span class="sxs-lookup"><span data-stu-id="630a0-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="630a0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="630a0-107">Remarks</span></span>  
 <span data-ttu-id="630a0-108">El con elementos genéricos `GetExactType` método reemplaza a ambos el [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) y [ICorDebugValue:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) métodos, cada uno de los que devuelven información sobre el tipo de un valor .</span><span class="sxs-lookup"><span data-stu-id="630a0-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="630a0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="630a0-109">Requirements</span></span>  
 <span data-ttu-id="630a0-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="630a0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="630a0-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="630a0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="630a0-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="630a0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="630a0-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="630a0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="630a0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="630a0-114">See Also</span></span>  
 
