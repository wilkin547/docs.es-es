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
ms.openlocfilehash: 6c6ff428e378e973d8846674ffacdcd04b2dbdbc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378346"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="a6f45-102">Interfaz ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="a6f45-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="a6f45-103">Proporciona métodos que administran un valor que es una referencia a un objeto.</span><span class="sxs-lookup"><span data-stu-id="a6f45-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="a6f45-104">(Es decir, esta interfaz proporciona métodos que administran un puntero). Esta interfaz implementa "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="a6f45-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6f45-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a6f45-105">Methods</span></span>  
  
|<span data-ttu-id="a6f45-106">Método</span><span class="sxs-lookup"><span data-stu-id="a6f45-106">Method</span></span>|<span data-ttu-id="a6f45-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6f45-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6f45-108">Método Dereference</span><span class="sxs-lookup"><span data-stu-id="a6f45-108">Dereference Method</span></span>](icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="a6f45-109">Obtiene el objeto al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="a6f45-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="a6f45-110">Método DereferenceStrong</span><span class="sxs-lookup"><span data-stu-id="a6f45-110">DereferenceStrong Method</span></span>](icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="a6f45-111">No implementado.</span><span class="sxs-lookup"><span data-stu-id="a6f45-111">Not implemented.</span></span> <span data-ttu-id="a6f45-112">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="a6f45-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="a6f45-113">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="a6f45-113">GetValue Method</span></span>](icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="a6f45-114">Obtiene la dirección de memoria actual del objeto al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="a6f45-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="a6f45-115">Método IsNull</span><span class="sxs-lookup"><span data-stu-id="a6f45-115">IsNull Method</span></span>](icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="a6f45-116">Obtiene un valor que indica si `ICorDebugReferenceValue` se trata de un valor null, en cuyo caso `ICorDebugReferenceValue` no apunta a un objeto.</span><span class="sxs-lookup"><span data-stu-id="a6f45-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="a6f45-117">Método SetValue</span><span class="sxs-lookup"><span data-stu-id="a6f45-117">SetValue Method</span></span>](icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="a6f45-118">Establece la dirección de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="a6f45-118">Sets the current memory address.</span></span> <span data-ttu-id="a6f45-119">Es decir, este método establece esto `ICorDebugReferenceValue` para que apunte a un objeto.</span><span class="sxs-lookup"><span data-stu-id="a6f45-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6f45-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a6f45-120">Remarks</span></span>  
 <span data-ttu-id="a6f45-121">El Common Language Runtime (CLR) puede realizar una recolección de elementos no utilizados en objetos cuando continúa el proceso depurado.</span><span class="sxs-lookup"><span data-stu-id="a6f45-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="a6f45-122">La recolección de elementos no utilizados puede mover objetos alrededor de la memoria.</span><span class="sxs-lookup"><span data-stu-id="a6f45-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="a6f45-123">Un `ICorDebugReferenceValue` objeto cooperará con la recolección de elementos no utilizados para que su información se actualice después de la recolección de elementos no utilizados o se invalidará implícitamente antes de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a6f45-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="a6f45-124">El `ICorDebugReferenceValue` objeto se puede invalidar implícitamente una vez que se ha continuado el proceso depurado.</span><span class="sxs-lookup"><span data-stu-id="a6f45-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="a6f45-125">La "ICorDebugHandleValue" derivada no se invalida hasta que se libera o expone explícitamente.</span><span class="sxs-lookup"><span data-stu-id="a6f45-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6f45-126">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a6f45-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6f45-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6f45-127">Requirements</span></span>  
 <span data-ttu-id="a6f45-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6f45-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6f45-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6f45-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6f45-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6f45-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6f45-131">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6f45-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f45-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6f45-132">See also</span></span>

- [<span data-ttu-id="a6f45-133">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a6f45-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
