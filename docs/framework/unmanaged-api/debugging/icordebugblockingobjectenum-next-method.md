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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 889c3bb2d5e0cd1feb9e592e667d47dedd4ede36
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171150"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="95f29-102">ICorDebugBlockingObjectEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="95f29-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="95f29-103">Obtiene el número especificado de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objetos de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="95f29-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95f29-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95f29-104">Syntax</span></span>  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="95f29-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="95f29-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="95f29-106">[in] El número de objetos que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="95f29-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="95f29-107">[out] Una matriz de punteros a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objetos.</span><span class="sxs-lookup"><span data-stu-id="95f29-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="95f29-108">[out] Un puntero al número de objetos que se recuperaron.</span><span class="sxs-lookup"><span data-stu-id="95f29-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95f29-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="95f29-109">Return Value</span></span>  
 <span data-ttu-id="95f29-110">Este método devuelve los siguientes HRESULT concretos.</span><span class="sxs-lookup"><span data-stu-id="95f29-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="95f29-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95f29-111">HRESULT</span></span>|<span data-ttu-id="95f29-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="95f29-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95f29-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="95f29-113">S_OK</span></span>|<span data-ttu-id="95f29-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="95f29-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="95f29-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="95f29-115">S_FALSE</span></span>|`pceltFetched` <span data-ttu-id="95f29-116">No es igual a `celt`.</span><span class="sxs-lookup"><span data-stu-id="95f29-116">does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95f29-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="95f29-117">Remarks</span></span>  
 <span data-ttu-id="95f29-118">Este método funciona como un enumerador COM típico.</span><span class="sxs-lookup"><span data-stu-id="95f29-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="95f29-119">Los valores de la matriz de entrada deben ser al menos del tamaño `celt`.</span><span class="sxs-lookup"><span data-stu-id="95f29-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="95f29-120">La matriz se rellenará con cualquiera siguiente `celt` si hay menos de los valores de la enumeración o con todos los valores restantes `celt` permanecen.</span><span class="sxs-lookup"><span data-stu-id="95f29-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="95f29-121">Cuando este método finaliza, `pceltFetched` se rellenará con el número de valores que se recuperaron.</span><span class="sxs-lookup"><span data-stu-id="95f29-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="95f29-122">Si `values` contiene punteros no válidos o apunta a un búfer que es menor que `celt`, o si `pceltFetched` es un puntero no válido, el resultado es indefinido.</span><span class="sxs-lookup"><span data-stu-id="95f29-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95f29-123">Aunque el [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructura no tiene que liberarse, debe ser liberado la interfaz "ICorDebugValue" dentro de él.</span><span class="sxs-lookup"><span data-stu-id="95f29-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95f29-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="95f29-124">Requirements</span></span>  
 <span data-ttu-id="95f29-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95f29-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95f29-126">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95f29-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95f29-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95f29-127">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="95f29-128">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="95f29-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="95f29-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="95f29-129">See also</span></span>

- [<span data-ttu-id="95f29-130">ICorDebugDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="95f29-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="95f29-131">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="95f29-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="95f29-132">Depuración</span><span class="sxs-lookup"><span data-stu-id="95f29-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
