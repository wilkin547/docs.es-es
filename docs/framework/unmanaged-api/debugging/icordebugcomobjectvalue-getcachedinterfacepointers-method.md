---
description: 'Más información sobre: ICorDebugComObjectValue:: Getcachedinterfacepointers ((método)'
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
ms.openlocfilehash: 737d71f6aa903a3dfa97f583b47a322ec074147f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710860"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="a3ede-103">ICorDebugComObjectValue::GetCachedInterfacePointers (Método)</span><span class="sxs-lookup"><span data-stu-id="a3ede-103">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>

<span data-ttu-id="a3ede-104">Obtiene los punteros de interfaz sin formato almacenados en memoria caché en el contenedor RCW (Runtime Callable wrapper) actual.</span><span class="sxs-lookup"><span data-stu-id="a3ede-104">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3ede-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3ede-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3ede-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3ede-106">Parameters</span></span>  

 `bIInspectableOnly`  
 <span data-ttu-id="a3ede-107">de Valor que indica si el método devolverá solo Windows Runtime interfaces ( `IInspectable` interfaces) o todas las interfaces com almacenadas en caché por el contenedor RCW (Runtime Callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="a3ede-107">[in] A value that indicates whether the method will return only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="a3ede-108">de El número de objetos cuyas direcciones se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="a3ede-108">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a3ede-109">enuncia Puntero al número de `CORDB_ADDRESS` valores realmente devueltos en `ptrs` .</span><span class="sxs-lookup"><span data-stu-id="a3ede-109">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="a3ede-110">Puntero a la dirección de inicio de una matriz de `CORDB_ADDRESS` valores que contienen las direcciones de los objetos de interfaz almacenados en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a3ede-110">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3ede-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a3ede-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3ede-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3ede-112">Requirements</span></span>  

 <span data-ttu-id="a3ede-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3ede-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3ede-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3ede-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3ede-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3ede-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3ede-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3ede-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ede-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3ede-117">See also</span></span>

- [<span data-ttu-id="a3ede-118">Interfaz ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="a3ede-118">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="a3ede-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a3ede-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
