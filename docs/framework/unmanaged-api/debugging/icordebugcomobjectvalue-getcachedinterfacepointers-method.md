---
title: ICorDebugComObjectValue::GetCachedInterfacePointers (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
ms.openlocfilehash: 9d1d6d2f506086dd3204053b0b635da2e7cdc87e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783961"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="c9fd8-102">ICorDebugComObjectValue::GetCachedInterfacePointers (Método)</span><span class="sxs-lookup"><span data-stu-id="c9fd8-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="c9fd8-103">Obtiene los punteros de interfaz sin formato almacenados en memoria caché en el contenedor RCW (Runtime Callable wrapper) actual.</span><span class="sxs-lookup"><span data-stu-id="c9fd8-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9fd8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9fd8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9fd8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c9fd8-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="c9fd8-106">de Valor que indica si el método devolverá solo Windows Runtime interfaces (interfaces`IInspectable`) o todas las interfaces COM almacenadas en caché por el contenedor RCW (Runtime Callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="c9fd8-106">[in] A value that indicates whether the method will return only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="c9fd8-107">de El número de objetos cuyas direcciones se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="c9fd8-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c9fd8-108">enuncia Puntero al número de valores `CORDB_ADDRESS` realmente devueltos en `ptrs`.</span><span class="sxs-lookup"><span data-stu-id="c9fd8-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="c9fd8-109">Puntero a la dirección de inicio de una matriz de valores de `CORDB_ADDRESS` que contienen las direcciones de los objetos de interfaz almacenados en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="c9fd8-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9fd8-110">Notas</span><span class="sxs-lookup"><span data-stu-id="c9fd8-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9fd8-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c9fd8-111">Requirements</span></span>  
 <span data-ttu-id="c9fd8-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9fd8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9fd8-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9fd8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9fd8-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9fd8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9fd8-115">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9fd8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9fd8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9fd8-116">See also</span></span>

- [<span data-ttu-id="c9fd8-117">ICorDebugComObjectValue (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9fd8-117">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="c9fd8-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c9fd8-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
