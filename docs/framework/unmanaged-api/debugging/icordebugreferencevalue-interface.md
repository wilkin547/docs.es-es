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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6575acfb1f75cbc8e3d59ddca5fea0953274cf2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206465"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="716e4-102">Interfaz ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="716e4-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="716e4-103">Proporciona métodos que administran un valor que es una referencia a un objeto.</span><span class="sxs-lookup"><span data-stu-id="716e4-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="716e4-104">(Es decir, esta interfaz proporciona métodos que administran un puntero). Esta interfaz implementa "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="716e4-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="716e4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="716e4-105">Methods</span></span>  
  
|<span data-ttu-id="716e4-106">Método</span><span class="sxs-lookup"><span data-stu-id="716e4-106">Method</span></span>|<span data-ttu-id="716e4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="716e4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="716e4-108">Método Dereference</span><span class="sxs-lookup"><span data-stu-id="716e4-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="716e4-109">Obtiene el objeto que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="716e4-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="716e4-110">Método DereferenceStrong</span><span class="sxs-lookup"><span data-stu-id="716e4-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="716e4-111">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="716e4-111">Not implemented.</span></span> <span data-ttu-id="716e4-112">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="716e4-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="716e4-113">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="716e4-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="716e4-114">Obtiene la dirección de memoria actual del objeto que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="716e4-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="716e4-115">Método IsNull</span><span class="sxs-lookup"><span data-stu-id="716e4-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="716e4-116">Obtiene un valor que indica si este `ICorDebugReferenceValue` es un valor null, en cuyo caso el `ICorDebugReferenceValue` no apunta a un objeto.</span><span class="sxs-lookup"><span data-stu-id="716e4-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="716e4-117">Método SetValue</span><span class="sxs-lookup"><span data-stu-id="716e4-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="716e4-118">Establece la dirección de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="716e4-118">Sets the current memory address.</span></span> <span data-ttu-id="716e4-119">Es decir, este método establece esto `ICorDebugReferenceValue` para que apunte a un objeto.</span><span class="sxs-lookup"><span data-stu-id="716e4-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="716e4-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="716e4-120">Remarks</span></span>  
 <span data-ttu-id="716e4-121">Common language runtime (CLR) puede hacer una recolección en objetos cuando se continúa el proceso depurado.</span><span class="sxs-lookup"><span data-stu-id="716e4-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="716e4-122">La colección de elementos no utilizados puede mover los objetos en memoria.</span><span class="sxs-lookup"><span data-stu-id="716e4-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="716e4-123">Un `ICorDebugReferenceValue` cualquiera cooperarán con la recolección de elementos para que su información se actualiza después de la recolección de elementos no utilizados o quedarán invalidado implícitamente antes de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="716e4-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="716e4-124">La `ICorDebugReferenceValue` objeto puede invalidar implícitamente después de que se ha reanudado el proceso depurado.</span><span class="sxs-lookup"><span data-stu-id="716e4-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="716e4-125">No se invalida la derivada "ICorDebugHandleValue" hasta que se publicó o se exponen explícitamente.</span><span class="sxs-lookup"><span data-stu-id="716e4-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="716e4-126">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="716e4-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="716e4-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="716e4-127">Requirements</span></span>  
 <span data-ttu-id="716e4-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="716e4-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="716e4-129">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="716e4-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="716e4-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="716e4-130">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="716e4-131">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="716e4-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="716e4-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="716e4-132">See also</span></span>

- [<span data-ttu-id="716e4-133">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="716e4-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
