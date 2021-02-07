---
description: 'Más información sobre: ICorDebugBlockingObjectEnum:: Next (método)'
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
ms.openlocfilehash: 66999ebf333c7115790b56afc1dc1d1ab7c47d69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711822"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="88e9a-103">ICorDebugBlockingObjectEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="88e9a-103">ICorDebugBlockingObjectEnum::Next Method</span></span>

<span data-ttu-id="88e9a-104">Obtiene el número especificado de objetos [CorDebugBlockingObject](cordebugblockingobject-structure.md) de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="88e9a-104">Gets the specified number of [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88e9a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88e9a-105">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="88e9a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="88e9a-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="88e9a-107">de Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="88e9a-107">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="88e9a-108">enuncia Matriz de punteros a objetos [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="88e9a-108">[out] An array of pointers to [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="88e9a-109">enuncia Puntero al número de objetos recuperados.</span><span class="sxs-lookup"><span data-stu-id="88e9a-109">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88e9a-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="88e9a-110">Return Value</span></span>  

 <span data-ttu-id="88e9a-111">Este método devuelve los siguientes HRESULT concretos.</span><span class="sxs-lookup"><span data-stu-id="88e9a-111">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="88e9a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="88e9a-112">HRESULT</span></span>|<span data-ttu-id="88e9a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="88e9a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="88e9a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="88e9a-114">S_OK</span></span>|<span data-ttu-id="88e9a-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="88e9a-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="88e9a-116">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="88e9a-116">S_FALSE</span></span>|<span data-ttu-id="88e9a-117">`pceltFetched` no es igual a `celt`.</span><span class="sxs-lookup"><span data-stu-id="88e9a-117">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88e9a-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="88e9a-118">Remarks</span></span>  

 <span data-ttu-id="88e9a-119">Este método funciona como un enumerador COM típico.</span><span class="sxs-lookup"><span data-stu-id="88e9a-119">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="88e9a-120">Los valores de la matriz de entrada deben tener al menos el tamaño `celt` .</span><span class="sxs-lookup"><span data-stu-id="88e9a-120">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="88e9a-121">La matriz se rellenará con los siguientes `celt` valores de la enumeración o con todos los valores restantes si no `celt` quedan menos.</span><span class="sxs-lookup"><span data-stu-id="88e9a-121">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="88e9a-122">Cuando este método devuelve `pceltFetched` un valor, se rellenará con el número de valores recuperados.</span><span class="sxs-lookup"><span data-stu-id="88e9a-122">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="88e9a-123">Si `values` contiene punteros no válidos o apunta a un búfer menor que `celt` , o si `pceltFetched` es un puntero no válido, el resultado es indefinido.</span><span class="sxs-lookup"><span data-stu-id="88e9a-123">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88e9a-124">Aunque no es necesario liberar la estructura [CorDebugBlockingObject](cordebugblockingobject-structure.md) , es necesario liberar la interfaz "ICorDebugValue" dentro de ella.</span><span class="sxs-lookup"><span data-stu-id="88e9a-124">Although the [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88e9a-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88e9a-125">Requirements</span></span>  

 <span data-ttu-id="88e9a-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88e9a-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88e9a-127">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88e9a-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88e9a-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88e9a-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88e9a-129">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88e9a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88e9a-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="88e9a-130">See also</span></span>

- [<span data-ttu-id="88e9a-131">ICorDebugDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88e9a-131">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="88e9a-132">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="88e9a-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="88e9a-133">Depuración</span><span class="sxs-lookup"><span data-stu-id="88e9a-133">Debugging</span></span>](index.md)
