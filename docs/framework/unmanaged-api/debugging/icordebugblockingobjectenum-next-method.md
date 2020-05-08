---
title: ICorDebugBlockingObjectEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
ms.openlocfilehash: 0ef49d2d833841eac62b2b964a0fdc902b4fb6a9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894773"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="a003a-102">ICorDebugBlockingObjectEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="a003a-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="a003a-103">Obtiene el número especificado de objetos [CorDebugBlockingObject](cordebugblockingobject-structure.md) de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="a003a-103">Gets the specified number of [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a003a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a003a-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a003a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a003a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a003a-106">de Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="a003a-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="a003a-107">enuncia Matriz de punteros a objetos [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="a003a-107">[out] An array of pointers to [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a003a-108">enuncia Puntero al número de objetos recuperados.</span><span class="sxs-lookup"><span data-stu-id="a003a-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a003a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a003a-109">Return Value</span></span>  
 <span data-ttu-id="a003a-110">Este método devuelve los siguientes HRESULT concretos.</span><span class="sxs-lookup"><span data-stu-id="a003a-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="a003a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a003a-111">HRESULT</span></span>|<span data-ttu-id="a003a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a003a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a003a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a003a-113">S_OK</span></span>|<span data-ttu-id="a003a-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a003a-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="a003a-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a003a-115">S_FALSE</span></span>|<span data-ttu-id="a003a-116">`pceltFetched` no es igual a `celt`.</span><span class="sxs-lookup"><span data-stu-id="a003a-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a003a-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a003a-117">Remarks</span></span>  
 <span data-ttu-id="a003a-118">Este método funciona como un enumerador COM típico.</span><span class="sxs-lookup"><span data-stu-id="a003a-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="a003a-119">Los valores de la matriz de entrada deben tener al `celt`menos el tamaño.</span><span class="sxs-lookup"><span data-stu-id="a003a-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="a003a-120">La matriz se rellenará con los siguientes `celt` valores de la enumeración o con todos los valores restantes si `celt` no quedan menos.</span><span class="sxs-lookup"><span data-stu-id="a003a-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="a003a-121">Cuando este método devuelve un `pceltFetched` valor, se rellenará con el número de valores recuperados.</span><span class="sxs-lookup"><span data-stu-id="a003a-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="a003a-122">Si `values` contiene punteros no válidos o apunta a un búfer menor que `celt`, o si `pceltFetched` es un puntero no válido, el resultado es indefinido.</span><span class="sxs-lookup"><span data-stu-id="a003a-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a003a-123">Aunque no es necesario liberar la estructura [CorDebugBlockingObject](cordebugblockingobject-structure.md) , es necesario liberar la interfaz "ICorDebugValue" dentro de ella.</span><span class="sxs-lookup"><span data-stu-id="a003a-123">Although the [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a003a-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a003a-124">Requirements</span></span>  
 <span data-ttu-id="a003a-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a003a-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a003a-126">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a003a-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a003a-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a003a-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a003a-128">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a003a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a003a-129">Consulta también</span><span class="sxs-lookup"><span data-stu-id="a003a-129">See also</span></span>

- [<span data-ttu-id="a003a-130">ICorDebugDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a003a-130">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="a003a-131">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a003a-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a003a-132">Depuración</span><span class="sxs-lookup"><span data-stu-id="a003a-132">Debugging</span></span>](index.md)
