---
title: COR_GC_REFERENCE (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_REFERENCE
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_GC_REFERENCE
helpviewer_keywords: COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 11be45743bd215315139fb77f016e85bc9b592c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="corgcreference-structure"></a><span data-ttu-id="943e2-102">COR_GC_REFERENCE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="943e2-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="943e2-103">Contiene información sobre un objeto que se va a recolectar con elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="943e2-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="943e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="943e2-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="943e2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="943e2-105">Members</span></span>  
  
|<span data-ttu-id="943e2-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="943e2-106">Member</span></span>|<span data-ttu-id="943e2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="943e2-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="943e2-108">Un puntero al dominio de aplicación a la que pertenece el identificador o el objeto.</span><span class="sxs-lookup"><span data-stu-id="943e2-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="943e2-109">Su valor puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="943e2-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="943e2-110">ICorDebugValue o en una ICorDebugReferenceValue (interfaz) que corresponde al objeto al que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="943e2-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="943e2-111">A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valor de enumeración que indica de dónde procede la raíz.</span><span class="sxs-lookup"><span data-stu-id="943e2-111">A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="943e2-112">Para obtener más información, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="943e2-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="943e2-113">Datos adicionales sobre el objeto al que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="943e2-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="943e2-114">Esta información depende del origen del objeto, tal y como indica la `type` campo.</span><span class="sxs-lookup"><span data-stu-id="943e2-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="943e2-115">Para obtener más información, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="943e2-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="943e2-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="943e2-116">Remarks</span></span>  
 <span data-ttu-id="943e2-117">El `type` campo es un [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valor de enumeración que indica de dónde procede la referencia.</span><span class="sxs-lookup"><span data-stu-id="943e2-117">The `type` field is a [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="943e2-118">Un determinado `COR_GC_REFERENCE` valor puede reflejar cualquiera de los siguientes tipos de objetos administrados:</span><span class="sxs-lookup"><span data-stu-id="943e2-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
-   <span data-ttu-id="943e2-119">Objetos de todas las pilas administradas (`CorGCReferenceType.CorReferenceStack`).</span><span class="sxs-lookup"><span data-stu-id="943e2-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="943e2-120">Esto incluye referencias directas en código administrado, así como los objetos creados por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="943e2-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
-   <span data-ttu-id="943e2-121">Objetos de la tabla de identificadores (`CorGCReferenceType.CorHandle*`).</span><span class="sxs-lookup"><span data-stu-id="943e2-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="943e2-122">Esto incluye las referencias fuertes (`HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT`) y las variables estáticas en un módulo.</span><span class="sxs-lookup"><span data-stu-id="943e2-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
-   <span data-ttu-id="943e2-123">Objetos de la cola del finalizador (`CorGCReferenceType.CorReferenceFinalizer`).</span><span class="sxs-lookup"><span data-stu-id="943e2-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="943e2-124">La cola del finalizador raíces de objetos hasta que ha ejecutado el finalizador.</span><span class="sxs-lookup"><span data-stu-id="943e2-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="943e2-125">El `extraData` campo contiene datos adicionales según el origen (o tipo) de la referencia.</span><span class="sxs-lookup"><span data-stu-id="943e2-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="943e2-126">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="943e2-126">Possible values are:</span></span>  
  
-   <span data-ttu-id="943e2-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="943e2-127">`DependentSource`.</span></span> <span data-ttu-id="943e2-128">Si el `type` es `CorGCREferenceType.CorHandleStrongDependent`, este campo es el objeto que, si se activa, raíces del objeto para que la recolección en `COR_GC_REFERENCE.Location`.</span><span class="sxs-lookup"><span data-stu-id="943e2-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
-   <span data-ttu-id="943e2-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="943e2-129">`RefCount`.</span></span> <span data-ttu-id="943e2-130">Si el `type` es `CorGCREferenceType.CorHandleStrongRefCount`, este campo es el recuento de referencias del identificador.</span><span class="sxs-lookup"><span data-stu-id="943e2-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
-   <span data-ttu-id="943e2-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="943e2-131">`Size`.</span></span> <span data-ttu-id="943e2-132">Si el `type` es `CorGCREferenceType.CorHandleStrongSizedByref`, este campo es el último tamaño del árbol de objetos para el que el recolector de elementos no utilizados calcula las raíces de objeto.</span><span class="sxs-lookup"><span data-stu-id="943e2-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="943e2-133">Tenga en cuenta que este cálculo no es necesariamente actualizado.</span><span class="sxs-lookup"><span data-stu-id="943e2-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="943e2-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="943e2-134">Requirements</span></span>  
 <span data-ttu-id="943e2-135">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="943e2-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="943e2-136">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="943e2-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="943e2-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="943e2-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="943e2-138">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="943e2-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="943e2-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="943e2-139">See Also</span></span>  
 [<span data-ttu-id="943e2-140">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="943e2-140">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="943e2-141">Depuración</span><span class="sxs-lookup"><span data-stu-id="943e2-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
