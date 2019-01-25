---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54ac36f6d0dba92742ea7a7acfadc194930ccd74
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516452"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="b2c9d-102">CorGCReferenceType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b2c9d-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="b2c9d-103">Identifica el origen de un objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2c9d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2c9d-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="b2c9d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b2c9d-105">Members</span></span>  
  
|<span data-ttu-id="b2c9d-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="b2c9d-106">Member name</span></span>|<span data-ttu-id="b2c9d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2c9d-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="b2c9d-108">Identificador a una referencia segura de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="b2c9d-109">Identificador de referencia segura anclada de la tabla de identificadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="b2c9d-110">Identificador de una referencia débil de la tabla de identificadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="b2c9d-111">Identificador de la tabla de identificadores de objeto a un objeto con recuento de referencias débil.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="b2c9d-112">Identificador de un objeto de recuento de referencias de la tabla de identificadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="b2c9d-113">Identificador de un objeto dependiente de la tabla de identificadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="b2c9d-114">Objeto anclado asincrónico de la tabla de identificadores de objetos.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="b2c9d-115">Identificador seguro que mantiene un tamaño aproximado del cierre colectivo de todos los objetos y raíces de objetos en tiempo de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="b2c9d-116">Referencia de la pila administrada.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="b2c9d-117">Referencia de la cola del finalizador.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="b2c9d-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="b2c9d-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="b2c9d-119">Devolver solo las referencias fuertes de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="b2c9d-120">Este valor se usa por la [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo método.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="b2c9d-121">Devolver solo las referencias débiles de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="b2c9d-122">Este valor se usa por la [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo método.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="b2c9d-123">Devolver todas las referencias de la tabla de identificadores.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-123">Return all references from the handle table.</span></span> <span data-ttu-id="b2c9d-124">Este valor se usa por la [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo método.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2c9d-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2c9d-125">Remarks</span></span>  
 <span data-ttu-id="b2c9d-126">El `CorGCReferenceType` enumeración se utiliza como sigue:</span><span class="sxs-lookup"><span data-stu-id="b2c9d-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
-   <span data-ttu-id="b2c9d-127">Como el valor de la `type` campo de la [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) estructura, indica el origen de una referencia o un identificador.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-127">As the value of the `type` field of the [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
-   <span data-ttu-id="b2c9d-128">Como el `types` argumento para el [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) método, especifica los tipos de controladores para incluir en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="b2c9d-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2c9d-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2c9d-129">Requirements</span></span>  
 <span data-ttu-id="b2c9d-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2c9d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2c9d-131">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2c9d-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2c9d-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2c9d-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2c9d-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2c9d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2c9d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2c9d-134">See also</span></span>
- [<span data-ttu-id="b2c9d-135">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="b2c9d-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
