---
description: 'Más información acerca de: estructura de COR_GC_REFERENCE'
title: COR_GC_REFERENCE (Estructura)
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
ms.openlocfilehash: 38518bb1eb870081621bf32af9e63cdaa208dbd3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801818"
---
# <a name="cor_gc_reference-structure"></a><span data-ttu-id="7a937-103">COR_GC_REFERENCE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="7a937-103">COR_GC_REFERENCE Structure</span></span>

<span data-ttu-id="7a937-104">Contiene información sobre un objeto que se va a recolectar con elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="7a937-104">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a937-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a937-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="7a937-106">Members</span><span class="sxs-lookup"><span data-stu-id="7a937-106">Members</span></span>  
  
|<span data-ttu-id="7a937-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="7a937-107">Member</span></span>|<span data-ttu-id="7a937-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a937-108">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="7a937-109">Puntero al dominio de aplicación al que pertenece el identificador u objeto.</span><span class="sxs-lookup"><span data-stu-id="7a937-109">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="7a937-110">Su valor puede ser `null` .</span><span class="sxs-lookup"><span data-stu-id="7a937-110">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="7a937-111">Una interfaz ICorDebugValue o ICorDebugReferenceValue que corresponde al objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="7a937-111">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="7a937-112">Un valor de enumeración de [corgcreferencetype (](corgcreferencetype-enumeration.md) que indica de dónde procede la raíz.</span><span class="sxs-lookup"><span data-stu-id="7a937-112">A [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="7a937-113">Para obtener más información, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="7a937-113">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="7a937-114">Datos adicionales sobre el objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="7a937-114">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="7a937-115">Esta información depende del origen del objeto, como se indica en el `type` campo.</span><span class="sxs-lookup"><span data-stu-id="7a937-115">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="7a937-116">Para obtener más información, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="7a937-116">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a937-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7a937-117">Remarks</span></span>  

 <span data-ttu-id="7a937-118">El `type` campo es un valor de enumeración [corgcreferencetype (](corgcreferencetype-enumeration.md) que indica de dónde procede la referencia.</span><span class="sxs-lookup"><span data-stu-id="7a937-118">The `type` field is a [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="7a937-119">Un `COR_GC_REFERENCE` valor determinado puede reflejar cualquiera de los siguientes tipos de objetos administrados:</span><span class="sxs-lookup"><span data-stu-id="7a937-119">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="7a937-120">Objetos de todas las pilas administradas ( `CorGCReferenceType.CorReferenceStack` ).</span><span class="sxs-lookup"><span data-stu-id="7a937-120">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="7a937-121">Esto incluye las referencias dinámicas en el código administrado, así como los objetos creados por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="7a937-121">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="7a937-122">Objetos de la tabla de identificadores ( `CorGCReferenceType.CorHandle*` ).</span><span class="sxs-lookup"><span data-stu-id="7a937-122">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="7a937-123">Esto incluye referencias seguras ( `HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT` ) y variables estáticas en un módulo.</span><span class="sxs-lookup"><span data-stu-id="7a937-123">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="7a937-124">Objetos de la cola del finalizador ( `CorGCReferenceType.CorReferenceFinalizer` ).</span><span class="sxs-lookup"><span data-stu-id="7a937-124">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="7a937-125">Los objetos raíces de la cola del finalizador hasta que se haya ejecutado el finalizador.</span><span class="sxs-lookup"><span data-stu-id="7a937-125">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="7a937-126">El `extraData` campo contiene datos adicionales en función del origen (o tipo) de la referencia.</span><span class="sxs-lookup"><span data-stu-id="7a937-126">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="7a937-127">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7a937-127">Possible values are:</span></span>  
  
- <span data-ttu-id="7a937-128">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="7a937-128">`DependentSource`.</span></span> <span data-ttu-id="7a937-129">Si `type` es `CorGCREferenceType.CorHandleStrongDependent` , este campo es el objeto que, si está activo, es la raíz del objeto en el que se va a realizar la recolección de elementos no utilizados `COR_GC_REFERENCE.Location` .</span><span class="sxs-lookup"><span data-stu-id="7a937-129">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="7a937-130">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="7a937-130">`RefCount`.</span></span> <span data-ttu-id="7a937-131">Si `type` es `CorGCREferenceType.CorHandleStrongRefCount` , este campo es el recuento de referencias del identificador.</span><span class="sxs-lookup"><span data-stu-id="7a937-131">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="7a937-132">`Size`.</span><span class="sxs-lookup"><span data-stu-id="7a937-132">`Size`.</span></span> <span data-ttu-id="7a937-133">Si `type` es `CorGCREferenceType.CorHandleStrongSizedByref` , este campo es el último tamaño del árbol de objetos para el que el recolector de elementos no utilizados calculó las raíces del objeto.</span><span class="sxs-lookup"><span data-stu-id="7a937-133">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="7a937-134">Tenga en cuenta que este cálculo no está necesariamente actualizado.</span><span class="sxs-lookup"><span data-stu-id="7a937-134">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a937-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a937-135">Requirements</span></span>  

 <span data-ttu-id="7a937-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a937-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a937-137">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a937-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a937-138">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a937-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a937-139">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a937-139">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a937-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a937-140">See also</span></span>

- [<span data-ttu-id="7a937-141">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="7a937-141">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="7a937-142">Depuración</span><span class="sxs-lookup"><span data-stu-id="7a937-142">Debugging</span></span>](index.md)
