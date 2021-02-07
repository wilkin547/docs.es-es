---
description: 'Más información acerca de: ICorDebugReferenceValue (interfaz)'
title: Interfaz ICorDebugReferenceValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
ms.openlocfilehash: e516b1178b4f4268472dedd37d6443e673e16af6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690969"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="3b2ca-103">Interfaz ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="3b2ca-103">ICorDebugReferenceValue Interface</span></span>

<span data-ttu-id="3b2ca-104">Proporciona métodos que administran un valor que es una referencia a un objeto.</span><span class="sxs-lookup"><span data-stu-id="3b2ca-104">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="3b2ca-105">(Es decir, esta interfaz proporciona métodos que administran un puntero). Esta interfaz implementa "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="3b2ca-105">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b2ca-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="3b2ca-106">Methods</span></span>  
  
|<span data-ttu-id="3b2ca-107">Método</span><span class="sxs-lookup"><span data-stu-id="3b2ca-107">Method</span></span>|<span data-ttu-id="3b2ca-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b2ca-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3b2ca-109">Método Dereference</span><span class="sxs-lookup"><span data-stu-id="3b2ca-109">Dereference Method</span></span>](icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="3b2ca-110">Obtiene el objeto al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="3b2ca-110">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="3b2ca-111">Método DereferenceStrong</span><span class="sxs-lookup"><span data-stu-id="3b2ca-111">DereferenceStrong Method</span></span>](icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="3b2ca-112">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="3b2ca-112">Not implemented.</span></span> <span data-ttu-id="3b2ca-113">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="3b2ca-113">Do not call this method.</span></span>|  
|[<span data-ttu-id="3b2ca-114">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="3b2ca-114">GetValue Method</span></span>](icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="3b2ca-115">Obtiene la dirección de memoria actual del objeto al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="3b2ca-115">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="3b2ca-116">Método IsNull</span><span class="sxs-lookup"><span data-stu-id="3b2ca-116">IsNull Method</span></span>](icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="3b2ca-117">Obtiene un valor que indica si `ICorDebugReferenceValue` se trata de un valor null, en cuyo caso `ICorDebugReferenceValue` no apunta a un objeto.</span><span class="sxs-lookup"><span data-stu-id="3b2ca-117">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="3b2ca-118">Método SetValue</span><span class="sxs-lookup"><span data-stu-id="3b2ca-118">SetValue Method</span></span>](icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="3b2ca-119">Establece la dirección de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="3b2ca-119">Sets the current memory address.</span></span> <span data-ttu-id="3b2ca-120">Es decir, este método establece esto `ICorDebugReferenceValue` para que apunte a un objeto.</span><span class="sxs-lookup"><span data-stu-id="3b2ca-120">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b2ca-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3b2ca-121">Remarks</span></span>  

 <span data-ttu-id="3b2ca-122">El Common Language Runtime (CLR) puede realizar una recolección de elementos no utilizados en objetos cuando continúa el proceso depurado.</span><span class="sxs-lookup"><span data-stu-id="3b2ca-122">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="3b2ca-123">La recolección de elementos no utilizados puede mover objetos alrededor de la memoria.</span><span class="sxs-lookup"><span data-stu-id="3b2ca-123">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="3b2ca-124">Un `ICorDebugReferenceValue` objeto cooperará con la recolección de elementos no utilizados para que su información se actualice después de la recolección de elementos no utilizados o se invalidará implícitamente antes de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3b2ca-124">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="3b2ca-125">El `ICorDebugReferenceValue` objeto se puede invalidar implícitamente una vez que se ha continuado el proceso depurado.</span><span class="sxs-lookup"><span data-stu-id="3b2ca-125">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="3b2ca-126">La "ICorDebugHandleValue" derivada no se invalida hasta que se libera o expone explícitamente.</span><span class="sxs-lookup"><span data-stu-id="3b2ca-126">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b2ca-127">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3b2ca-127">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b2ca-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b2ca-128">Requirements</span></span>  

 <span data-ttu-id="3b2ca-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b2ca-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b2ca-130">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b2ca-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b2ca-131">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b2ca-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b2ca-132">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b2ca-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b2ca-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b2ca-133">See also</span></span>

- [<span data-ttu-id="3b2ca-134">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3b2ca-134">Debugging Interfaces</span></span>](debugging-interfaces.md)
