---
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
ms.openlocfilehash: bb4a8f7ff3ee54474804e3e5620dcce7c9f79fb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726618"
---
# <a name="cor_gc_reference-structure"></a><span data-ttu-id="289f2-102">COR_GC_REFERENCE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="289f2-102">COR_GC_REFERENCE Structure</span></span>

<span data-ttu-id="289f2-103">Contiene información sobre un objeto que se va a recolectar con elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="289f2-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="289f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="289f2-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="289f2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="289f2-105">Members</span></span>  
  
|<span data-ttu-id="289f2-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="289f2-106">Member</span></span>|<span data-ttu-id="289f2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="289f2-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="289f2-108">Puntero al dominio de aplicación al que pertenece el identificador u objeto.</span><span class="sxs-lookup"><span data-stu-id="289f2-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="289f2-109">Su valor puede ser `null` .</span><span class="sxs-lookup"><span data-stu-id="289f2-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="289f2-110">Una interfaz ICorDebugValue o ICorDebugReferenceValue que corresponde al objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="289f2-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="289f2-111">Un valor de enumeración de [corgcreferencetype (](corgcreferencetype-enumeration.md) que indica de dónde procede la raíz.</span><span class="sxs-lookup"><span data-stu-id="289f2-111">A [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="289f2-112">Para obtener más información, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="289f2-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="289f2-113">Datos adicionales sobre el objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="289f2-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="289f2-114">Esta información depende del origen del objeto, como se indica en el `type` campo.</span><span class="sxs-lookup"><span data-stu-id="289f2-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="289f2-115">Para obtener más información, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="289f2-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="289f2-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="289f2-116">Remarks</span></span>  

 <span data-ttu-id="289f2-117">El `type` campo es un valor de enumeración [corgcreferencetype (](corgcreferencetype-enumeration.md) que indica de dónde procede la referencia.</span><span class="sxs-lookup"><span data-stu-id="289f2-117">The `type` field is a [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="289f2-118">Un `COR_GC_REFERENCE` valor determinado puede reflejar cualquiera de los siguientes tipos de objetos administrados:</span><span class="sxs-lookup"><span data-stu-id="289f2-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="289f2-119">Objetos de todas las pilas administradas ( `CorGCReferenceType.CorReferenceStack` ).</span><span class="sxs-lookup"><span data-stu-id="289f2-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="289f2-120">Esto incluye las referencias dinámicas en el código administrado, así como los objetos creados por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="289f2-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="289f2-121">Objetos de la tabla de identificadores ( `CorGCReferenceType.CorHandle*` ).</span><span class="sxs-lookup"><span data-stu-id="289f2-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="289f2-122">Esto incluye referencias seguras ( `HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT` ) y variables estáticas en un módulo.</span><span class="sxs-lookup"><span data-stu-id="289f2-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="289f2-123">Objetos de la cola del finalizador ( `CorGCReferenceType.CorReferenceFinalizer` ).</span><span class="sxs-lookup"><span data-stu-id="289f2-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="289f2-124">Los objetos raíces de la cola del finalizador hasta que se haya ejecutado el finalizador.</span><span class="sxs-lookup"><span data-stu-id="289f2-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="289f2-125">El `extraData` campo contiene datos adicionales en función del origen (o tipo) de la referencia.</span><span class="sxs-lookup"><span data-stu-id="289f2-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="289f2-126">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="289f2-126">Possible values are:</span></span>  
  
- <span data-ttu-id="289f2-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="289f2-127">`DependentSource`.</span></span> <span data-ttu-id="289f2-128">Si `type` es `CorGCREferenceType.CorHandleStrongDependent` , este campo es el objeto que, si está activo, es la raíz del objeto en el que se va a realizar la recolección de elementos no utilizados `COR_GC_REFERENCE.Location` .</span><span class="sxs-lookup"><span data-stu-id="289f2-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="289f2-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="289f2-129">`RefCount`.</span></span> <span data-ttu-id="289f2-130">Si `type` es `CorGCREferenceType.CorHandleStrongRefCount` , este campo es el recuento de referencias del identificador.</span><span class="sxs-lookup"><span data-stu-id="289f2-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="289f2-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="289f2-131">`Size`.</span></span> <span data-ttu-id="289f2-132">Si `type` es `CorGCREferenceType.CorHandleStrongSizedByref` , este campo es el último tamaño del árbol de objetos para el que el recolector de elementos no utilizados calculó las raíces del objeto.</span><span class="sxs-lookup"><span data-stu-id="289f2-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="289f2-133">Tenga en cuenta que este cálculo no está necesariamente actualizado.</span><span class="sxs-lookup"><span data-stu-id="289f2-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="289f2-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="289f2-134">Requirements</span></span>  

 <span data-ttu-id="289f2-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="289f2-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="289f2-136">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="289f2-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="289f2-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="289f2-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="289f2-138">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="289f2-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="289f2-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="289f2-139">See also</span></span>

- [<span data-ttu-id="289f2-140">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="289f2-140">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="289f2-141">Depuración</span><span class="sxs-lookup"><span data-stu-id="289f2-141">Debugging</span></span>](index.md)
