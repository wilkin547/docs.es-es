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
ms.openlocfilehash: cb5bec66ab02de248109d8aaf444a93e67c2c6d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720365"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="3c860-102">ICorDebugValue2::GetExactType (Método)</span><span class="sxs-lookup"><span data-stu-id="3c860-102">ICorDebugValue2::GetExactType Method</span></span>

<span data-ttu-id="3c860-103">Obtiene un puntero de interfaz a un objeto "ICorDebugType" que representa el <xref:System.Type> de este valor.</span><span class="sxs-lookup"><span data-stu-id="3c860-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c860-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c860-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c860-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c860-105">Parameters</span></span>  

 `ppType`  
 <span data-ttu-id="3c860-106">enuncia Puntero a la dirección de un `ICorDebugType` objeto que representa el <xref:System.Type> del valor representado por este objeto "ICorDebugValue2".</span><span class="sxs-lookup"><span data-stu-id="3c860-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c860-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c860-107">Remarks</span></span>  

 <span data-ttu-id="3c860-108">El método compatible con genéricos `GetExactType` sustituye a los métodos [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) y [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , cada uno de los cuales devuelve información sobre el tipo de un valor.</span><span class="sxs-lookup"><span data-stu-id="3c860-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c860-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c860-109">Requirements</span></span>  

 <span data-ttu-id="3c860-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c860-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c860-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c860-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c860-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c860-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c860-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c860-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c860-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c860-114">See also</span></span>
