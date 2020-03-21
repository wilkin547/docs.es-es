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
ms.openlocfilehash: e22269b76c230f702f4712298fddcd0df1fde50d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179325"
---
# <a name="cor_gc_reference-structure"></a><span data-ttu-id="a1749-102">COR_GC_REFERENCE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="a1749-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="a1749-103">Contiene información sobre un objeto que se va a recolectar con elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="a1749-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1749-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1749-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="a1749-105">Members</span><span class="sxs-lookup"><span data-stu-id="a1749-105">Members</span></span>  
  
|<span data-ttu-id="a1749-106">Member</span><span class="sxs-lookup"><span data-stu-id="a1749-106">Member</span></span>|<span data-ttu-id="a1749-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1749-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="a1749-108">Puntero al dominio de aplicación al que pertenece el identificador o el objeto.</span><span class="sxs-lookup"><span data-stu-id="a1749-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="a1749-109">Su valor `null`puede ser .</span><span class="sxs-lookup"><span data-stu-id="a1749-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="a1749-110">Un ICorDebugValue o un ICorDebugReferenceValue interfaz que corresponde al objeto que se va a recopilar como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a1749-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="a1749-111">Un valor de enumeración [CorGCReferenceType](corgcreferencetype-enumeration.md) que indica de dónde procede la raíz.</span><span class="sxs-lookup"><span data-stu-id="a1749-111">A [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="a1749-112">Para obtener más información, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="a1749-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="a1749-113">Datos adicionales sobre el objeto que se va a recopilar.</span><span class="sxs-lookup"><span data-stu-id="a1749-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="a1749-114">Esta información depende del origen del objeto, `type` como se indica en el campo.</span><span class="sxs-lookup"><span data-stu-id="a1749-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="a1749-115">Para obtener más información, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="a1749-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1749-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a1749-116">Remarks</span></span>  
 <span data-ttu-id="a1749-117">El `type` campo es un valor de enumeración [CorGCReferenceType](corgcreferencetype-enumeration.md) que indica de dónde procede la referencia.</span><span class="sxs-lookup"><span data-stu-id="a1749-117">The `type` field is a [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="a1749-118">Un `COR_GC_REFERENCE` valor determinado puede reflejar cualquiera de los siguientes tipos de objetos administrados:</span><span class="sxs-lookup"><span data-stu-id="a1749-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="a1749-119">Objetos de todas`CorGCReferenceType.CorReferenceStack`las pilas administradas ( ).</span><span class="sxs-lookup"><span data-stu-id="a1749-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="a1749-120">Esto incluye referencias en vivo en código administrado, así como objetos creados por Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a1749-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="a1749-121">Objetos de la`CorGCReferenceType.CorHandle*`tabla de identificadores ( ).</span><span class="sxs-lookup"><span data-stu-id="a1749-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="a1749-122">Esto incluye referencias`HNDTYPE_STRONG` `HNDTYPE_REFCOUNT`seguras ( y ) y variables estáticas en un módulo.</span><span class="sxs-lookup"><span data-stu-id="a1749-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="a1749-123">Objetos de la`CorGCReferenceType.CorReferenceFinalizer`cola del finalizador ( ).</span><span class="sxs-lookup"><span data-stu-id="a1749-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="a1749-124">El finalizador enraiza los objetos hasta que se ha ejecutado el finalizador.</span><span class="sxs-lookup"><span data-stu-id="a1749-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="a1749-125">El `extraData` campo contiene datos adicionales en función del origen (o tipo) de la referencia.</span><span class="sxs-lookup"><span data-stu-id="a1749-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="a1749-126">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="a1749-126">Possible values are:</span></span>  
  
- <span data-ttu-id="a1749-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="a1749-127">`DependentSource`.</span></span> <span data-ttu-id="a1749-128">Si `type` es `CorGCREferenceType.CorHandleStrongDependent`, este campo es el objeto que, si está vivo, arraiga el objeto que se va a recopilar como elementos no utilizados en `COR_GC_REFERENCE.Location`.</span><span class="sxs-lookup"><span data-stu-id="a1749-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="a1749-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="a1749-129">`RefCount`.</span></span> <span data-ttu-id="a1749-130">Si `type` es `CorGCREferenceType.CorHandleStrongRefCount`, este campo es el recuento de referencias del identificador.</span><span class="sxs-lookup"><span data-stu-id="a1749-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="a1749-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="a1749-131">`Size`.</span></span> <span data-ttu-id="a1749-132">Si `type` es `CorGCREferenceType.CorHandleStrongSizedByref`, este campo es el último tamaño del árbol de objetos para el que el recolector de elementos no utilizados calculó las raíces del objeto.</span><span class="sxs-lookup"><span data-stu-id="a1749-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="a1749-133">Tenga en cuenta que este cálculo no está necesariamente actualizado.</span><span class="sxs-lookup"><span data-stu-id="a1749-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1749-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1749-134">Requirements</span></span>  
 <span data-ttu-id="a1749-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1749-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1749-136">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1749-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1749-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1749-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1749-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1749-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1749-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1749-139">See also</span></span>

- [<span data-ttu-id="a1749-140">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="a1749-140">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="a1749-141">Depuración</span><span class="sxs-lookup"><span data-stu-id="a1749-141">Debugging</span></span>](index.md)
