---
title: ICorDebugGCReferenceEnum (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGCReferenceEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGCReferenceEnum
helpviewer_keywords: ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 89e516bba3d9dd8a13e1beb2bdc231b0a639dbf0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="b0e80-102">ICorDebugGCReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0e80-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="b0e80-103">Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b0e80-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b0e80-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b0e80-104">Methods</span></span>  
  
|<span data-ttu-id="b0e80-105">Método</span><span class="sxs-lookup"><span data-stu-id="b0e80-105">Method</span></span>|<span data-ttu-id="b0e80-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0e80-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b0e80-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="b0e80-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="b0e80-108">Obtiene el número especificado de [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instancias que contienen información acerca de los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b0e80-108">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0e80-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b0e80-109">Remarks</span></span>  
 <span data-ttu-id="b0e80-110">El `ICorDebugGCReferenceEnum` interfaz implementa la interfaz "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="b0e80-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="b0e80-111">Un `ICorDebugGCReferenceEnum` instancia se rellena con [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instancias mediante una llamada a la [icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b0e80-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="b0e80-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) pueden enumerar objetos mediante una llamada a la [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b0e80-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="b0e80-113">El [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objetos de la colección que se rellena con este método representan tres tipos de objetos:</span><span class="sxs-lookup"><span data-stu-id="b0e80-113">The [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
-   <span data-ttu-id="b0e80-114">Objetos de todas las pilas administradas.</span><span class="sxs-lookup"><span data-stu-id="b0e80-114">Objects from all managed stacks.</span></span> <span data-ttu-id="b0e80-115">Esto incluye referencias directas en código administrado, así como los objetos creados por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="b0e80-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
-   <span data-ttu-id="b0e80-116">Objetos de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="b0e80-116">Objects from the handle table.</span></span> <span data-ttu-id="b0e80-117">Esto incluye las referencias fuertes (`HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT`) y las variables estáticas en un módulo.</span><span class="sxs-lookup"><span data-stu-id="b0e80-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
-   <span data-ttu-id="b0e80-118">Objetos de la cola del finalizador.</span><span class="sxs-lookup"><span data-stu-id="b0e80-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="b0e80-119">La cola del finalizador raíces de objetos hasta que ha ejecutado el finalizador.</span><span class="sxs-lookup"><span data-stu-id="b0e80-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0e80-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0e80-120">Requirements</span></span>  
 <span data-ttu-id="b0e80-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0e80-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0e80-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0e80-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0e80-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0e80-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0e80-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0e80-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e80-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0e80-125">See Also</span></span>  
 [<span data-ttu-id="b0e80-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b0e80-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
