---
title: CorGCReferenceType (enumeración)
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
ms.openlocfilehash: 17d47b6242bb12ff5ca3cfbde3e4ec183b9c19fc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793873"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="0ee77-102">CorGCReferenceType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="0ee77-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="0ee77-103">Identifica el origen de un objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="0ee77-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ee77-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ee77-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0ee77-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0ee77-105">Members</span></span>  
  
|<span data-ttu-id="0ee77-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="0ee77-106">Member name</span></span>|<span data-ttu-id="0ee77-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ee77-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="0ee77-108">Identificador a una referencia segura de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="0ee77-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="0ee77-109">Identificador de una referencia segura anclada de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="0ee77-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="0ee77-110">Identificador de una referencia débil de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="0ee77-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="0ee77-111">Identificador de un objeto de cuenta de referencia débil de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="0ee77-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="0ee77-112">Identificador de un objeto con recuento de referencias de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="0ee77-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="0ee77-113">Identificador de un objeto dependiente de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="0ee77-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="0ee77-114">Objeto anclado asincrónico de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="0ee77-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="0ee77-115">Identificador seguro que mantiene un tamaño aproximado del cierre colectivo de todos los objetos y raíces de objetos en tiempo de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0ee77-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="0ee77-116">Referencia de la pila administrada.</span><span class="sxs-lookup"><span data-stu-id="0ee77-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="0ee77-117">Referencia de la cola del finalizador.</span><span class="sxs-lookup"><span data-stu-id="0ee77-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="0ee77-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="0ee77-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="0ee77-119">Devuelve solo las referencias fuertes de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="0ee77-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="0ee77-120">Este valor solo lo usa el método [ICorDebugProcess5:: enumeratehandles (](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0ee77-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="0ee77-121">Devuelve solo las referencias débiles de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="0ee77-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="0ee77-122">Este valor solo lo usa el método [ICorDebugProcess5:: enumeratehandles (](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0ee77-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="0ee77-123">Devuelve todas las referencias de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="0ee77-123">Return all references from the handle table.</span></span> <span data-ttu-id="0ee77-124">Este valor solo lo usa el método [ICorDebugProcess5:: enumeratehandles (](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0ee77-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ee77-125">Notas</span><span class="sxs-lookup"><span data-stu-id="0ee77-125">Remarks</span></span>  
 <span data-ttu-id="0ee77-126">La enumeración `CorGCReferenceType` se utiliza como sigue:</span><span class="sxs-lookup"><span data-stu-id="0ee77-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
- <span data-ttu-id="0ee77-127">Como valor del campo `type` de la estructura [COR_GC_REFERENCE](cor-gc-reference-structure.md) , indica el origen de una referencia o un identificador.</span><span class="sxs-lookup"><span data-stu-id="0ee77-127">As the value of the `type` field of the [COR_GC_REFERENCE](cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
- <span data-ttu-id="0ee77-128">Como `types` argumento al método [ICorDebugProcess5:: enumeratehandles (](icordebugprocess5-enumeratehandles-method.md) , especifica los tipos de identificadores que se van a incluir en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="0ee77-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ee77-129">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="0ee77-129">Requirements</span></span>  
 <span data-ttu-id="0ee77-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ee77-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ee77-131">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ee77-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ee77-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ee77-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ee77-133">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ee77-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee77-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ee77-134">See also</span></span>

- [<span data-ttu-id="0ee77-135">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="0ee77-135">Debugging Enumerations</span></span>](debugging-enumerations.md)
