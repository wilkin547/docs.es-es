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
ms.openlocfilehash: 002e53d380140a63297a90baa270b5a6f1e5e328
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192269"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="f809d-102">ICorDebugValue2::GetExactType (Método)</span><span class="sxs-lookup"><span data-stu-id="f809d-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="f809d-103">Obtiene un puntero de interfaz a un objeto "ICorDebugType" que representa el <xref:System.Type> de este valor.</span><span class="sxs-lookup"><span data-stu-id="f809d-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f809d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f809d-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f809d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f809d-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="f809d-106">[out] Un puntero a la dirección de un `ICorDebugType` objeto que representa el <xref:System.Type> del valor representado por este objeto "ICorDebugValue2".</span><span class="sxs-lookup"><span data-stu-id="f809d-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f809d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f809d-107">Remarks</span></span>  
 <span data-ttu-id="f809d-108">El con elementos genéricos `GetExactType` método reemplaza a ambos el [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) y [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) métodos, cada uno de los que devuelven información sobre el tipo de valor .</span><span class="sxs-lookup"><span data-stu-id="f809d-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f809d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f809d-109">Requirements</span></span>  
 <span data-ttu-id="f809d-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f809d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f809d-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f809d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f809d-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f809d-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f809d-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f809d-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f809d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f809d-114">See also</span></span>
