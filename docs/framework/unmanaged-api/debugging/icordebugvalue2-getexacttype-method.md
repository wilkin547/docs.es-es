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
ms.openlocfilehash: 6c5e5d1c9f734e097fc9e871d7a0cffdc9bb9138
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791121"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="ae8b9-102">ICorDebugValue2::GetExactType (Método)</span><span class="sxs-lookup"><span data-stu-id="ae8b9-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="ae8b9-103">Obtiene un puntero de interfaz a un objeto "ICorDebugType" que representa el <xref:System.Type> de este valor.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae8b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae8b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae8b9-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ae8b9-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="ae8b9-106">enuncia Puntero a la dirección de un objeto `ICorDebugType` que representa el <xref:System.Type> del valor representado por este objeto "ICorDebugValue2".</span><span class="sxs-lookup"><span data-stu-id="ae8b9-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae8b9-107">Notas</span><span class="sxs-lookup"><span data-stu-id="ae8b9-107">Remarks</span></span>  
 <span data-ttu-id="ae8b9-108">El método `GetExactType` compatible con genéricos reemplaza a los métodos [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) y [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , cada uno de los cuales devuelve información sobre el tipo de un valor.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae8b9-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="ae8b9-109">Requirements</span></span>  
 <span data-ttu-id="ae8b9-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae8b9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae8b9-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae8b9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae8b9-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae8b9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae8b9-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae8b9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae8b9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae8b9-114">See also</span></span>
