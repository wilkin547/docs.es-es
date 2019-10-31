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
ms.openlocfilehash: 3a1c4a931a61186c4737aada47ceb861e7848e7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122832"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="4190f-102">ICorDebugBlockingObjectEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="4190f-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="4190f-103">Obtiene el número especificado de objetos [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="4190f-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4190f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4190f-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4190f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4190f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4190f-106">de Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="4190f-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="4190f-107">enuncia Matriz de punteros a objetos [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="4190f-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="4190f-108">enuncia Puntero al número de objetos recuperados.</span><span class="sxs-lookup"><span data-stu-id="4190f-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4190f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4190f-109">Return Value</span></span>  
 <span data-ttu-id="4190f-110">Este método devuelve los siguientes HRESULT concretos.</span><span class="sxs-lookup"><span data-stu-id="4190f-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="4190f-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4190f-111">HRESULT</span></span>|<span data-ttu-id="4190f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4190f-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4190f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="4190f-113">S_OK</span></span>|<span data-ttu-id="4190f-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="4190f-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="4190f-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4190f-115">S_FALSE</span></span>|<span data-ttu-id="4190f-116">`pceltFetched` no es igual a `celt`.</span><span class="sxs-lookup"><span data-stu-id="4190f-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4190f-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4190f-117">Remarks</span></span>  
 <span data-ttu-id="4190f-118">Este método funciona como un enumerador COM típico.</span><span class="sxs-lookup"><span data-stu-id="4190f-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="4190f-119">Los valores de la matriz de entrada deben tener al menos el tamaño `celt`.</span><span class="sxs-lookup"><span data-stu-id="4190f-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="4190f-120">La matriz se rellenará con los valores de `celt` siguientes en la enumeración o con todos los valores restantes si se mantiene menos de `celt`.</span><span class="sxs-lookup"><span data-stu-id="4190f-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="4190f-121">Cuando este método devuelve un valor, `pceltFetched` se rellenará con el número de valores recuperados.</span><span class="sxs-lookup"><span data-stu-id="4190f-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="4190f-122">Si `values` contiene punteros no válidos o apunta a un búfer menor que `celt`, o si `pceltFetched` es un puntero no válido, el resultado es indefinido.</span><span class="sxs-lookup"><span data-stu-id="4190f-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4190f-123">Aunque no es necesario liberar la estructura [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) , es necesario liberar la interfaz "ICorDebugValue" dentro de ella.</span><span class="sxs-lookup"><span data-stu-id="4190f-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4190f-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4190f-124">Requirements</span></span>  
 <span data-ttu-id="4190f-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4190f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4190f-126">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4190f-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4190f-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4190f-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4190f-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4190f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4190f-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4190f-129">See also</span></span>

- [<span data-ttu-id="4190f-130">ICorDebugDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4190f-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="4190f-131">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4190f-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4190f-132">Depuración</span><span class="sxs-lookup"><span data-stu-id="4190f-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
