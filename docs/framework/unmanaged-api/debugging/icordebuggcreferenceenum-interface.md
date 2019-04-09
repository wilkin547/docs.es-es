---
title: ICorDebugGCReferenceEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f83d2ac9ca96145fa89b283fec42c71858097f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080836"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="f4555-102">ICorDebugGCReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4555-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="f4555-103">Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f4555-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4555-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f4555-104">Methods</span></span>  
  
|<span data-ttu-id="f4555-105">Método</span><span class="sxs-lookup"><span data-stu-id="f4555-105">Method</span></span>|<span data-ttu-id="f4555-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4555-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4555-107">Método Next</span><span class="sxs-lookup"><span data-stu-id="f4555-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="f4555-108">Obtiene el número especificado de [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instancias que contienen información sobre los objetos que se pueden recolectar.</span><span class="sxs-lookup"><span data-stu-id="f4555-108">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4555-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f4555-109">Remarks</span></span>  
 <span data-ttu-id="f4555-110">El `ICorDebugGCReferenceEnum` interfaz implementa la interfaz "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="f4555-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="f4555-111">Un `ICorDebugGCReferenceEnum` instancia se rellena con [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instancias mediante una llamada a la [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="f4555-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="f4555-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) se pueden enumerar objetos mediante una llamada a la [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="f4555-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="f4555-113">El [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objetos de la colección que se rellena mediante este método representan tres tipos de objetos:</span><span class="sxs-lookup"><span data-stu-id="f4555-113">The [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
-   <span data-ttu-id="f4555-114">Objetos de todas las pilas administradas.</span><span class="sxs-lookup"><span data-stu-id="f4555-114">Objects from all managed stacks.</span></span> <span data-ttu-id="f4555-115">Esto incluye referencias activas en código administrado, así como los objetos creados por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="f4555-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
-   <span data-ttu-id="f4555-116">Objetos de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="f4555-116">Objects from the handle table.</span></span> <span data-ttu-id="f4555-117">Esto incluye las referencias fuertes (`HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT`) y las variables estáticas en un módulo.</span><span class="sxs-lookup"><span data-stu-id="f4555-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
-   <span data-ttu-id="f4555-118">Objetos de la cola del finalizador.</span><span class="sxs-lookup"><span data-stu-id="f4555-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="f4555-119">La cola del finalizador raíces objetos hasta que se ha ejecutado el finalizador.</span><span class="sxs-lookup"><span data-stu-id="f4555-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4555-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4555-120">Requirements</span></span>  
 <span data-ttu-id="f4555-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4555-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4555-122">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4555-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4555-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4555-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f4555-124">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f4555-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f4555-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4555-125">See also</span></span>

- [<span data-ttu-id="f4555-126">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f4555-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
