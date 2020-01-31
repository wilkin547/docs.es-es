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
ms.openlocfilehash: f01c27376191c3a2dddf56dae4b26c8b5193c73e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788643"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="c8de1-102">ICorDebugGCReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c8de1-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="c8de1-103">Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c8de1-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8de1-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c8de1-104">Methods</span></span>  
  
|<span data-ttu-id="c8de1-105">Método</span><span class="sxs-lookup"><span data-stu-id="c8de1-105">Method</span></span>|<span data-ttu-id="c8de1-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8de1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c8de1-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="c8de1-107">Next Method</span></span>](icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="c8de1-108">Obtiene el número especificado de instancias de [COR_GC_REFERENCE](cor-gc-reference-structure.md) que contienen información sobre los objetos que se van a recolectar como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c8de1-108">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8de1-109">Notas</span><span class="sxs-lookup"><span data-stu-id="c8de1-109">Remarks</span></span>  
 <span data-ttu-id="c8de1-110">La interfaz de `ICorDebugGCReferenceEnum` implementa la interfaz "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="c8de1-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="c8de1-111">Una instancia de `ICorDebugGCReferenceEnum` se rellena con [COR_GC_REFERENCE](cor-gc-reference-structure.md) instancias mediante una llamada al método [ICorDebugProcess5:: enumerategcreferences (](icordebugprocess5-enumerategcreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c8de1-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="c8de1-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objetos se pueden enumerar llamando al método [ICorDebugGCReference:: Next](icordebuggcreferenceenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c8de1-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="c8de1-113">Los objetos [COR_GC_REFERENCE](cor-gc-reference-structure.md) de la colección rellenados por este método representan tres tipos de objetos:</span><span class="sxs-lookup"><span data-stu-id="c8de1-113">The [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="c8de1-114">Objetos de todas las pilas administradas.</span><span class="sxs-lookup"><span data-stu-id="c8de1-114">Objects from all managed stacks.</span></span> <span data-ttu-id="c8de1-115">Esto incluye las referencias dinámicas en código administrado, así como los objetos creados por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c8de1-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="c8de1-116">Objetos de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c8de1-116">Objects from the handle table.</span></span> <span data-ttu-id="c8de1-117">Esto incluye referencias fuertes (`HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT`) y variables estáticas en un módulo.</span><span class="sxs-lookup"><span data-stu-id="c8de1-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="c8de1-118">Objetos de la cola del finalizador.</span><span class="sxs-lookup"><span data-stu-id="c8de1-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="c8de1-119">Los objetos raíces de la cola del finalizador hasta que se haya ejecutado el finalizador.</span><span class="sxs-lookup"><span data-stu-id="c8de1-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8de1-120">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c8de1-120">Requirements</span></span>  
 <span data-ttu-id="c8de1-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8de1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8de1-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8de1-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8de1-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8de1-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8de1-124">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8de1-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8de1-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8de1-125">See also</span></span>

- [<span data-ttu-id="c8de1-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c8de1-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
