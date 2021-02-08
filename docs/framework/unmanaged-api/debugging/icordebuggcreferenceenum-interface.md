---
description: 'Más información acerca de: interfaz Icordebuggcreferenceenum ('
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
ms.openlocfilehash: ad4a61cdc2b30fb4c8e2be500eae878327c6b449
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801298"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="5c30f-103">ICorDebugGCReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c30f-103">ICorDebugGCReferenceEnum Interface</span></span>

<span data-ttu-id="5c30f-104">Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5c30f-104">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c30f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5c30f-105">Methods</span></span>  
  
|<span data-ttu-id="5c30f-106">Método</span><span class="sxs-lookup"><span data-stu-id="5c30f-106">Method</span></span>|<span data-ttu-id="5c30f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c30f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c30f-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="5c30f-108">Next Method</span></span>](icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="5c30f-109">Obtiene el número especificado de instancias de [COR_GC_REFERENCE](cor-gc-reference-structure.md) que contienen información sobre los objetos que se van a recolectar como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5c30f-109">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c30f-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5c30f-110">Remarks</span></span>  

 <span data-ttu-id="5c30f-111">La `ICorDebugGCReferenceEnum` interfaz implementa la interfaz "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="5c30f-111">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="5c30f-112">Una `ICorDebugGCReferenceEnum` instancia se rellena con [COR_GC_REFERENCE](cor-gc-reference-structure.md) instancias llamando al método [ICorDebugProcess5:: enumerategcreferences (](icordebugprocess5-enumerategcreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5c30f-112">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="5c30f-113">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objetos se pueden enumerar llamando al método [ICorDebugGCReference:: Next](icordebuggcreferenceenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5c30f-113">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="5c30f-114">Los objetos [COR_GC_REFERENCE](cor-gc-reference-structure.md) de la colección rellenados por este método representan tres tipos de objetos:</span><span class="sxs-lookup"><span data-stu-id="5c30f-114">The [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="5c30f-115">Objetos de todas las pilas administradas.</span><span class="sxs-lookup"><span data-stu-id="5c30f-115">Objects from all managed stacks.</span></span> <span data-ttu-id="5c30f-116">Esto incluye las referencias dinámicas en código administrado, así como los objetos creados por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="5c30f-116">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="5c30f-117">Objetos de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="5c30f-117">Objects from the handle table.</span></span> <span data-ttu-id="5c30f-118">Esto incluye referencias seguras ( `HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT` ) y variables estáticas en un módulo.</span><span class="sxs-lookup"><span data-stu-id="5c30f-118">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="5c30f-119">Objetos de la cola del finalizador.</span><span class="sxs-lookup"><span data-stu-id="5c30f-119">Objects from the finalizer queue.</span></span> <span data-ttu-id="5c30f-120">Los objetos raíces de la cola del finalizador hasta que se haya ejecutado el finalizador.</span><span class="sxs-lookup"><span data-stu-id="5c30f-120">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c30f-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c30f-121">Requirements</span></span>  

 <span data-ttu-id="5c30f-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c30f-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c30f-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c30f-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c30f-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c30f-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c30f-125">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c30f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c30f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c30f-126">See also</span></span>

- [<span data-ttu-id="5c30f-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5c30f-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
