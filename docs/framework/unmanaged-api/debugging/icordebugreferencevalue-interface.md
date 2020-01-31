---
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
ms.openlocfilehash: 2efba22b4ec372c5ddedd4982a29d66945d3511c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792125"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="67dc2-102">Interfaz ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="67dc2-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="67dc2-103">Proporciona métodos que administran un valor que es una referencia a un objeto.</span><span class="sxs-lookup"><span data-stu-id="67dc2-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="67dc2-104">(Es decir, esta interfaz proporciona métodos que administran un puntero). Esta interfaz implementa "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="67dc2-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67dc2-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="67dc2-105">Methods</span></span>  
  
|<span data-ttu-id="67dc2-106">Método</span><span class="sxs-lookup"><span data-stu-id="67dc2-106">Method</span></span>|<span data-ttu-id="67dc2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="67dc2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67dc2-108">Dereference (método)</span><span class="sxs-lookup"><span data-stu-id="67dc2-108">Dereference Method</span></span>](icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="67dc2-109">Obtiene el objeto al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67dc2-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="67dc2-110">DereferenceStrong (método)</span><span class="sxs-lookup"><span data-stu-id="67dc2-110">DereferenceStrong Method</span></span>](icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="67dc2-111">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="67dc2-111">Not implemented.</span></span> <span data-ttu-id="67dc2-112">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="67dc2-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="67dc2-113">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="67dc2-113">GetValue Method</span></span>](icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="67dc2-114">Obtiene la dirección de memoria actual del objeto al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67dc2-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="67dc2-115">IsNull (método)</span><span class="sxs-lookup"><span data-stu-id="67dc2-115">IsNull Method</span></span>](icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="67dc2-116">Obtiene un valor que indica si este `ICorDebugReferenceValue` es un valor null, en cuyo caso el `ICorDebugReferenceValue` no señala a un objeto.</span><span class="sxs-lookup"><span data-stu-id="67dc2-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="67dc2-117">SetValue (método)</span><span class="sxs-lookup"><span data-stu-id="67dc2-117">SetValue Method</span></span>](icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="67dc2-118">Establece la dirección de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="67dc2-118">Sets the current memory address.</span></span> <span data-ttu-id="67dc2-119">Es decir, este método establece este `ICorDebugReferenceValue` para que apunte a un objeto.</span><span class="sxs-lookup"><span data-stu-id="67dc2-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67dc2-120">Notas</span><span class="sxs-lookup"><span data-stu-id="67dc2-120">Remarks</span></span>  
 <span data-ttu-id="67dc2-121">El Common Language Runtime (CLR) puede realizar una recolección de elementos no utilizados en objetos cuando continúa el proceso depurado.</span><span class="sxs-lookup"><span data-stu-id="67dc2-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="67dc2-122">La recolección de elementos no utilizados puede mover objetos alrededor de la memoria.</span><span class="sxs-lookup"><span data-stu-id="67dc2-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="67dc2-123">Una `ICorDebugReferenceValue` cooperará con la recolección de elementos no utilizados para que su información se actualice después de la recolección de elementos no utilizados o se invalidará implícitamente antes de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="67dc2-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="67dc2-124">El objeto `ICorDebugReferenceValue` se puede invalidar implícitamente una vez que se ha continuado el proceso depurado.</span><span class="sxs-lookup"><span data-stu-id="67dc2-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="67dc2-125">La "ICorDebugHandleValue" derivada no se invalida hasta que se libera o expone explícitamente.</span><span class="sxs-lookup"><span data-stu-id="67dc2-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67dc2-126">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="67dc2-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67dc2-127">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="67dc2-127">Requirements</span></span>  
 <span data-ttu-id="67dc2-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67dc2-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67dc2-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67dc2-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67dc2-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67dc2-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67dc2-131">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67dc2-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67dc2-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="67dc2-132">See also</span></span>

- [<span data-ttu-id="67dc2-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="67dc2-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
