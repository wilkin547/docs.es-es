---
title: "ICorDebugBlockingObjectEnum::Next (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBlockingObjectEnum.Next Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c05420a54d7a79198e235a39e578bedf296b4fe9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="56f5a-102">ICorDebugBlockingObjectEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="56f5a-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="56f5a-103">Obtiene el número especificado de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objetos de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="56f5a-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56f5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56f5a-104">Syntax</span></span>  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingOjbect values[],  
             [out] ULONG *pceltFetched;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56f5a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56f5a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="56f5a-106">[in] El número de objetos que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="56f5a-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="56f5a-107">[out] Una matriz de punteros a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objetos.</span><span class="sxs-lookup"><span data-stu-id="56f5a-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="56f5a-108">[out] Un puntero al número de objetos que se recuperaron.</span><span class="sxs-lookup"><span data-stu-id="56f5a-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56f5a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="56f5a-109">Return Value</span></span>  
 <span data-ttu-id="56f5a-110">Este método devuelve los siguientes HRESULT concretos.</span><span class="sxs-lookup"><span data-stu-id="56f5a-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="56f5a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56f5a-111">HRESULT</span></span>|<span data-ttu-id="56f5a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="56f5a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="56f5a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="56f5a-113">S_OK</span></span>|<span data-ttu-id="56f5a-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="56f5a-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="56f5a-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="56f5a-115">S_FALSE</span></span>|<span data-ttu-id="56f5a-116">`pceltFetched` no es igual a `celt`.</span><span class="sxs-lookup"><span data-stu-id="56f5a-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56f5a-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="56f5a-117">Remarks</span></span>  
 <span data-ttu-id="56f5a-118">Este método funciona como un enumerador COM típico.</span><span class="sxs-lookup"><span data-stu-id="56f5a-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="56f5a-119">Los valores de la matriz de entrada deben ser al menos del tamaño `celt`.</span><span class="sxs-lookup"><span data-stu-id="56f5a-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="56f5a-120">La matriz se rellenará con en la siguiente `celt` si hay menos de los valores de la enumeración o con todos los valores restantes `celt` permanecen.</span><span class="sxs-lookup"><span data-stu-id="56f5a-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="56f5a-121">Cuando este método vuelve, `pceltFetched` se rellenará con el número de valores que se recuperaron.</span><span class="sxs-lookup"><span data-stu-id="56f5a-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="56f5a-122">Si `values` contiene punteros no válidos o apunta a un búfer que es menor que `celt`, o si `pceltFetched` es un puntero no válido, el resultado es indefinido.</span><span class="sxs-lookup"><span data-stu-id="56f5a-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56f5a-123">Aunque la [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) no es necesario que se liberen estructura, la interfaz de "ICorDebugValue" en su interior necesita que se liberen.</span><span class="sxs-lookup"><span data-stu-id="56f5a-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
-  
  
## <a name="requirements"></a><span data-ttu-id="56f5a-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56f5a-124">Requirements</span></span>  
 <span data-ttu-id="56f5a-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56f5a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56f5a-126">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56f5a-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56f5a-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56f5a-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56f5a-128">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56f5a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f5a-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="56f5a-129">See Also</span></span>  
 [<span data-ttu-id="56f5a-130">ICorDebugDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="56f5a-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="56f5a-131">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="56f5a-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="56f5a-132">Depuración</span><span class="sxs-lookup"><span data-stu-id="56f5a-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
