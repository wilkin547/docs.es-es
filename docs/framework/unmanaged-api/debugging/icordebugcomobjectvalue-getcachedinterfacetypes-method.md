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
ms.openlocfilehash: f5f0f11683043f1c287dd3ca3071830bcfb46502
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677562"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="46f62-102">ICorDebugComObjectValue::GetCachedInterfaceTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="46f62-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>

<span data-ttu-id="46f62-103">Proporciona un enumerador para los tipos de interfaz en los que se ha convertido el objeto actual o se ha utilizado como.</span><span class="sxs-lookup"><span data-stu-id="46f62-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46f62-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46f62-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46f62-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="46f62-105">Parameters</span></span>  

 `bIInspectableOnly`  
 <span data-ttu-id="46f62-106">de Valor que indica si el método devuelve solo Windows Runtime interfaces ( `IInspectable` interfaces) o todas las interfaces com almacenadas en caché por el contenedor RCW (Runtime Callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="46f62-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="46f62-107">enuncia Puntero a la dirección de un enumerador ICorDebugTypeEnum que proporciona acceso a los objetos ICorDebugType que representan los tipos de interfaz almacenados en memoria caché filtrados según `bIInspectableOnly` .</span><span class="sxs-lookup"><span data-stu-id="46f62-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46f62-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="46f62-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46f62-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46f62-109">Requirements</span></span>  

 <span data-ttu-id="46f62-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46f62-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46f62-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46f62-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46f62-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46f62-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46f62-113">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46f62-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46f62-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46f62-114">See also</span></span>

- [<span data-ttu-id="46f62-115">Interfaz ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="46f62-115">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="46f62-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="46f62-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
