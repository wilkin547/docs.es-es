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
ms.openlocfilehash: dcec97bac2aefc8db1f9351f1dacb0f36fc0d2a0
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396805"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="a5ad6-102">ICorDebugValue2::GetExactType (Método)</span><span class="sxs-lookup"><span data-stu-id="a5ad6-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="a5ad6-103">Obtiene un puntero de interfaz a un objeto "ICorDebugType" que representa el <xref:System.Type> de este valor.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ad6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5ad6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5ad6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5ad6-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="a5ad6-106">enuncia Puntero a la dirección de un `ICorDebugType` objeto que representa el <xref:System.Type> del valor representado por este objeto "ICorDebugValue2".</span><span class="sxs-lookup"><span data-stu-id="a5ad6-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5ad6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5ad6-107">Remarks</span></span>  
 <span data-ttu-id="a5ad6-108">El método compatible con genéricos `GetExactType` sustituye a los métodos [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) y [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , cada uno de los cuales devuelve información sobre el tipo de un valor.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5ad6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5ad6-109">Requirements</span></span>  
 <span data-ttu-id="a5ad6-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5ad6-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5ad6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5ad6-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5ad6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5ad6-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5ad6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ad6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5ad6-114">See also</span></span>
