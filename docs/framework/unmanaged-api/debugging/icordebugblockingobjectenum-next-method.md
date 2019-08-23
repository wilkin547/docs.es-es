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
ms.openlocfilehash: 1e94e4da0eea06ce9cc0110002b1def9e4dd4989
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939142"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="65a78-102">ICorDebugBlockingObjectEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="65a78-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="65a78-103">Obtiene el número especificado de objetos [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="65a78-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65a78-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65a78-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="65a78-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="65a78-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="65a78-106">de Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="65a78-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="65a78-107">enuncia Matriz de punteros a objetos [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="65a78-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="65a78-108">enuncia Puntero al número de objetos recuperados.</span><span class="sxs-lookup"><span data-stu-id="65a78-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65a78-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="65a78-109">Return Value</span></span>  
 <span data-ttu-id="65a78-110">Este método devuelve los siguientes HRESULT concretos.</span><span class="sxs-lookup"><span data-stu-id="65a78-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="65a78-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65a78-111">HRESULT</span></span>|<span data-ttu-id="65a78-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="65a78-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65a78-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="65a78-113">S_OK</span></span>|<span data-ttu-id="65a78-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="65a78-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="65a78-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="65a78-115">S_FALSE</span></span>|<span data-ttu-id="65a78-116">`pceltFetched` no es igual a `celt`.</span><span class="sxs-lookup"><span data-stu-id="65a78-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65a78-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="65a78-117">Remarks</span></span>  
 <span data-ttu-id="65a78-118">Este método funciona como un enumerador COM típico.</span><span class="sxs-lookup"><span data-stu-id="65a78-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="65a78-119">Los valores de la matriz de entrada deben tener al `celt`menos el tamaño.</span><span class="sxs-lookup"><span data-stu-id="65a78-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="65a78-120">La matriz se rellenará con los siguientes `celt` valores de la enumeración o con todos los valores restantes si `celt` no quedan menos.</span><span class="sxs-lookup"><span data-stu-id="65a78-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="65a78-121">Cuando este método devuelve un `pceltFetched` valor, se rellenará con el número de valores recuperados.</span><span class="sxs-lookup"><span data-stu-id="65a78-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="65a78-122">Si `values` contiene punteros no válidos o apunta a un búfer menor que `celt`, o si `pceltFetched` es un puntero no válido, el resultado es indefinido.</span><span class="sxs-lookup"><span data-stu-id="65a78-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="65a78-123">Aunque no es necesario liberar la estructura [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) , es necesario liberar la interfaz "ICorDebugValue" dentro de ella.</span><span class="sxs-lookup"><span data-stu-id="65a78-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65a78-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65a78-124">Requirements</span></span>  
 <span data-ttu-id="65a78-125">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65a78-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65a78-126">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="65a78-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65a78-127">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65a78-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65a78-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65a78-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a78-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="65a78-129">See also</span></span>

- [<span data-ttu-id="65a78-130">ICorDebugDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="65a78-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="65a78-131">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="65a78-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="65a78-132">Depuración</span><span class="sxs-lookup"><span data-stu-id="65a78-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
