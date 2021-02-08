---
description: 'Más información sobre: enumeración Corgcreferencetype ('
title: CorGCReferenceType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorGCReferenceType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorGCReferenceType
helpviewer_keywords:
- CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type:
- apiref
ms.openlocfilehash: a1f534f9fe4b9ba4ede0bef94f35cf1688fe1817
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801519"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="39dee-103">CorGCReferenceType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="39dee-103">CorGCReferenceType Enumeration</span></span>

<span data-ttu-id="39dee-104">Identifica el origen de un objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="39dee-104">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39dee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39dee-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a><span data-ttu-id="39dee-106">Members</span><span class="sxs-lookup"><span data-stu-id="39dee-106">Members</span></span>  
  
|<span data-ttu-id="39dee-107">Nombre del miembro</span><span class="sxs-lookup"><span data-stu-id="39dee-107">Member name</span></span>|<span data-ttu-id="39dee-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="39dee-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="39dee-109">Identificador a una referencia segura de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="39dee-109">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="39dee-110">Identificador de una referencia segura anclada de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="39dee-110">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="39dee-111">Identificador de una referencia débil de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="39dee-111">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="39dee-112">Identificador de un objeto de cuenta de referencia débil de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="39dee-112">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="39dee-113">Identificador de un objeto con recuento de referencias de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="39dee-113">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="39dee-114">Identificador de un objeto dependiente de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="39dee-114">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="39dee-115">Objeto anclado asincrónico de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="39dee-115">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="39dee-116">Identificador seguro que mantiene un tamaño aproximado del cierre colectivo de todos los objetos y raíces de objetos en tiempo de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="39dee-116">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="39dee-117">Referencia de la pila administrada.</span><span class="sxs-lookup"><span data-stu-id="39dee-117">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="39dee-118">Referencia de la cola del finalizador.</span><span class="sxs-lookup"><span data-stu-id="39dee-118">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="39dee-119">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="39dee-119">CorHandleStrongOnly</span></span>|<span data-ttu-id="39dee-120">Devuelve solo las referencias fuertes de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="39dee-120">Return only strong references from the handle table.</span></span> <span data-ttu-id="39dee-121">Este valor solo lo usa el método [ICorDebugProcess5:: enumeratehandles (](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="39dee-121">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="39dee-122">Devuelve solo las referencias débiles de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="39dee-122">Return only weak references from the handle table.</span></span> <span data-ttu-id="39dee-123">Este valor solo lo usa el método [ICorDebugProcess5:: enumeratehandles (](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="39dee-123">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="39dee-124">Devuelve todas las referencias de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="39dee-124">Return all references from the handle table.</span></span> <span data-ttu-id="39dee-125">Este valor solo lo usa el método [ICorDebugProcess5:: enumeratehandles (](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="39dee-125">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39dee-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="39dee-126">Remarks</span></span>  

 <span data-ttu-id="39dee-127">La `CorGCReferenceType` enumeración se usa como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="39dee-127">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
- <span data-ttu-id="39dee-128">Como valor del `type` campo de la estructura [COR_GC_REFERENCE](cor-gc-reference-structure.md) , indica el origen de una referencia o un identificador.</span><span class="sxs-lookup"><span data-stu-id="39dee-128">As the value of the `type` field of the [COR_GC_REFERENCE](cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
- <span data-ttu-id="39dee-129">Como `types` argumento para el método [ICorDebugProcess5:: enumeratehandles (](icordebugprocess5-enumeratehandles-method.md) , especifica los tipos de identificadores que se van a incluir en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="39dee-129">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39dee-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39dee-130">Requirements</span></span>  

 <span data-ttu-id="39dee-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39dee-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39dee-132">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39dee-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39dee-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39dee-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39dee-134">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39dee-134">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39dee-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="39dee-135">See also</span></span>

- [<span data-ttu-id="39dee-136">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="39dee-136">Debugging Enumerations</span></span>](debugging-enumerations.md)
