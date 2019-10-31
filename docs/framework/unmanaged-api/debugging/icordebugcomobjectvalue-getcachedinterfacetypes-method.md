---
title: ICorDebugComObjectValue::GetCachedInterfaceTypes (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
ms.openlocfilehash: 199f58456e64ccf7ef771d42d5c7d64b189cb670
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125496"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="89217-102">ICorDebugComObjectValue::GetCachedInterfaceTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="89217-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="89217-103">Proporciona un enumerador para los tipos de interfaz en los que se ha convertido el objeto actual o se ha utilizado como.</span><span class="sxs-lookup"><span data-stu-id="89217-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89217-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89217-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89217-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89217-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="89217-106">de Valor que indica si el método devuelve solo Windows Runtime interfaces (interfaces`IInspectable`) o todas las interfaces COM almacenadas en caché por el contenedor RCW (Runtime Callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="89217-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="89217-107">enuncia Puntero a la dirección de un enumerador ICorDebugTypeEnum que proporciona acceso a los objetos ICorDebugType que representan los tipos de interfaz almacenados en memoria caché filtrados según `bIInspectableOnly`.</span><span class="sxs-lookup"><span data-stu-id="89217-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89217-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89217-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89217-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89217-109">Requirements</span></span>  
 <span data-ttu-id="89217-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89217-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89217-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89217-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89217-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89217-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89217-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89217-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89217-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="89217-114">See also</span></span>

- [<span data-ttu-id="89217-115">ICorDebugComObjectValue (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89217-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="89217-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="89217-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
