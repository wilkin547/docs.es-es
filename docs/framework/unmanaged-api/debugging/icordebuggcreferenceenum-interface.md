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
ms.openlocfilehash: 5650a7e6e6cb0108f0d043914ea94debe2b703bf
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213106"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="10c2d-102">ICorDebugGCReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10c2d-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="10c2d-103">Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="10c2d-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10c2d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="10c2d-104">Methods</span></span>  
  
|<span data-ttu-id="10c2d-105">Método</span><span class="sxs-lookup"><span data-stu-id="10c2d-105">Method</span></span>|<span data-ttu-id="10c2d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="10c2d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10c2d-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="10c2d-107">Next Method</span></span>](icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="10c2d-108">Obtiene el número especificado de instancias de [COR_GC_REFERENCE](cor-gc-reference-structure.md) que contienen información sobre los objetos que se van a recolectar como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="10c2d-108">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10c2d-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="10c2d-109">Remarks</span></span>  
 <span data-ttu-id="10c2d-110">La `ICorDebugGCReferenceEnum` interfaz implementa la interfaz "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="10c2d-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="10c2d-111">Una `ICorDebugGCReferenceEnum` instancia se rellena con [COR_GC_REFERENCE](cor-gc-reference-structure.md) instancias llamando al método [ICorDebugProcess5:: enumerategcreferences (](icordebugprocess5-enumerategcreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="10c2d-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="10c2d-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objetos se pueden enumerar llamando al método [ICorDebugGCReference:: Next](icordebuggcreferenceenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="10c2d-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="10c2d-113">Los objetos [COR_GC_REFERENCE](cor-gc-reference-structure.md) de la colección rellenados por este método representan tres tipos de objetos:</span><span class="sxs-lookup"><span data-stu-id="10c2d-113">The [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="10c2d-114">Objetos de todas las pilas administradas.</span><span class="sxs-lookup"><span data-stu-id="10c2d-114">Objects from all managed stacks.</span></span> <span data-ttu-id="10c2d-115">Esto incluye las referencias dinámicas en código administrado, así como los objetos creados por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="10c2d-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="10c2d-116">Objetos de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="10c2d-116">Objects from the handle table.</span></span> <span data-ttu-id="10c2d-117">Esto incluye referencias seguras ( `HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT` ) y variables estáticas en un módulo.</span><span class="sxs-lookup"><span data-stu-id="10c2d-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="10c2d-118">Objetos de la cola del finalizador.</span><span class="sxs-lookup"><span data-stu-id="10c2d-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="10c2d-119">Los objetos raíces de la cola del finalizador hasta que se haya ejecutado el finalizador.</span><span class="sxs-lookup"><span data-stu-id="10c2d-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10c2d-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10c2d-120">Requirements</span></span>  
 <span data-ttu-id="10c2d-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10c2d-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10c2d-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10c2d-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10c2d-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10c2d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10c2d-124">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10c2d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10c2d-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10c2d-125">See also</span></span>

- [<span data-ttu-id="10c2d-126">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="10c2d-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
