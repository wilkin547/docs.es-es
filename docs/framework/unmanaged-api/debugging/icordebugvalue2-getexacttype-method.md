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
ms.openlocfilehash: 03d701d0801c55b6e91600f0767a6d737e4915c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479953"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="4ffce-102">ICorDebugValue2::GetExactType (Método)</span><span class="sxs-lookup"><span data-stu-id="4ffce-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="4ffce-103">Obtiene un puntero de interfaz a un objeto "ICorDebugType" que representa el <xref:System.Type> de este valor.</span><span class="sxs-lookup"><span data-stu-id="4ffce-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ffce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ffce-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ffce-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ffce-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="4ffce-106">[out] Un puntero a la dirección de un `ICorDebugType` objeto que representa el <xref:System.Type> del valor representado por este objeto "ICorDebugValue2".</span><span class="sxs-lookup"><span data-stu-id="4ffce-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ffce-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ffce-107">Remarks</span></span>  
 <span data-ttu-id="4ffce-108">El con elementos genéricos `GetExactType` método reemplaza a ambos el [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) y [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) métodos, cada uno de los que devuelven información sobre el tipo de valor .</span><span class="sxs-lookup"><span data-stu-id="4ffce-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ffce-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ffce-109">Requirements</span></span>  
 <span data-ttu-id="4ffce-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ffce-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ffce-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ffce-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ffce-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ffce-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ffce-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ffce-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ffce-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ffce-114">See also</span></span>

