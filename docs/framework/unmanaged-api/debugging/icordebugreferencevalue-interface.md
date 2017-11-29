---
title: ICorDebugReferenceValue Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue
helpviewer_keywords: ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d11cb4cbd6baa1e0d381c9fb11d5a3343287cf55
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugreferencevalue-interface1"></a><span data-ttu-id="b960c-102">ICorDebugReferenceValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="b960c-102">ICorDebugReferenceValue Interface1</span></span>
<span data-ttu-id="b960c-103">Proporciona métodos que administran un valor que es una referencia a un objeto.</span><span class="sxs-lookup"><span data-stu-id="b960c-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="b960c-104">(Es decir, esta interfaz proporciona métodos que administran un puntero). Esta interfaz implementa "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="b960c-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b960c-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b960c-105">Methods</span></span>  
  
|<span data-ttu-id="b960c-106">Método</span><span class="sxs-lookup"><span data-stu-id="b960c-106">Method</span></span>|<span data-ttu-id="b960c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b960c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b960c-108">Dereference (método)</span><span class="sxs-lookup"><span data-stu-id="b960c-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="b960c-109">Obtiene el objeto al que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="b960c-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="b960c-110">DereferenceStrong (método)</span><span class="sxs-lookup"><span data-stu-id="b960c-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="b960c-111">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="b960c-111">Not implemented.</span></span> <span data-ttu-id="b960c-112">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="b960c-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="b960c-113">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="b960c-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="b960c-114">Obtiene la dirección de memoria actual del objeto de referencia.</span><span class="sxs-lookup"><span data-stu-id="b960c-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="b960c-115">IsNull (método)</span><span class="sxs-lookup"><span data-stu-id="b960c-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="b960c-116">Obtiene un valor que indica si este `ICorDebugReferenceValue` es un valor null, en cuyo caso el `ICorDebugReferenceValue` no señala a un objeto.</span><span class="sxs-lookup"><span data-stu-id="b960c-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="b960c-117">SetValue (método)</span><span class="sxs-lookup"><span data-stu-id="b960c-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="b960c-118">Establece la dirección de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="b960c-118">Sets the current memory address.</span></span> <span data-ttu-id="b960c-119">Es decir, este método establece este `ICorDebugReferenceValue` para que apunte a un objeto.</span><span class="sxs-lookup"><span data-stu-id="b960c-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b960c-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b960c-120">Remarks</span></span>  
 <span data-ttu-id="b960c-121">Common language runtime (CLR) puede hacer una colección de elementos no utilizados en objetos cuando continúa el proceso depurado.</span><span class="sxs-lookup"><span data-stu-id="b960c-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="b960c-122">La colección de elementos no utilizados puede mover objetos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="b960c-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="b960c-123">Un `ICorDebugReferenceValue` en cooperación con la recolección de elementos para que su información se actualiza después de la recolección de elementos no utilizados o quedarán invalidado implícitamente antes de la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="b960c-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="b960c-124">La `ICorDebugReferenceValue` objeto puede invalidar implícitamente después de que se ha continuado el proceso depurado.</span><span class="sxs-lookup"><span data-stu-id="b960c-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="b960c-125">No se invalida la derivada "ICorDebugHandleValue" hasta que se publican o se exponen explícitamente.</span><span class="sxs-lookup"><span data-stu-id="b960c-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b960c-126">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="b960c-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b960c-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b960c-127">Requirements</span></span>  
 <span data-ttu-id="b960c-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b960c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b960c-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b960c-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b960c-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b960c-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b960c-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b960c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b960c-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b960c-132">See Also</span></span>  
    
    
 [<span data-ttu-id="b960c-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b960c-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
