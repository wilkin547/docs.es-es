---
title: "IMetaDataEmit::MergeEnd (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit.MergeEnd
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 265fc007b5817e8dffd5846738a7a0003bbddf9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="22650-102">IMetaDataEmit::MergeEnd (Método)</span><span class="sxs-lookup"><span data-stu-id="22650-102">IMetaDataEmit::MergeEnd Method</span></span>
<span data-ttu-id="22650-103">Definir el ámbito de mezclas en actual todos los ámbitos de metadatos especificados por una o más llamadas anteriores a [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span><span class="sxs-lookup"><span data-stu-id="22650-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22650-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22650-104">Syntax</span></span>  
  
```  
HRESULT MergeEnd ();  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22650-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="22650-105">Parameters</span></span>  
 <span data-ttu-id="22650-106">Este método no toma ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="22650-106">This method takes no parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22650-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22650-107">Remarks</span></span>  
 <span data-ttu-id="22650-108">Esta rutina desencadena la verdadera combinación de metadatos, de todos los ámbitos especificados por delante de las llamadas a de importación `IMetaDataEmit::Merge`, en el ámbito de salida actual.</span><span class="sxs-lookup"><span data-stu-id="22650-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>  
  
 <span data-ttu-id="22650-109">Las siguientes condiciones especiales se aplican a la combinación:</span><span class="sxs-lookup"><span data-stu-id="22650-109">The following special conditions apply to the merge:</span></span>  
  
-   <span data-ttu-id="22650-110">Nunca se importa un identificador de versión de módulo (MVID), porque es único para los metadatos en el ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="22650-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>  
  
-   <span data-ttu-id="22650-111">No todo el módulo de las propiedades existentes se sobrescriben.</span><span class="sxs-lookup"><span data-stu-id="22650-111">No existing module-wide properties are overwritten.</span></span>  
  
     <span data-ttu-id="22650-112">Si ya se han establecido las propiedades del módulo para el ámbito actual, no se importa ninguna propiedad de módulo.</span><span class="sxs-lookup"><span data-stu-id="22650-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="22650-113">Sin embargo, si las propiedades del módulo no se han configurado en el ámbito actual, se importan solo una vez, cuando se encuentran en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="22650-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="22650-114">Si se vuelven a encontrar esas propiedades de módulo, son duplicados.</span><span class="sxs-lookup"><span data-stu-id="22650-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="22650-115">Si se comparan los valores de todas las propiedades de módulo (excepto el MVID) y no se encuentran duplicados, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="22650-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>  
  
-   <span data-ttu-id="22650-116">Para obtener definiciones de tipo (`TypeDef`), duplicados no se combinan en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="22650-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="22650-117">`TypeDef`se comprueban los objetos duplicados en todas *nombre de objeto completo* + *GUID* + *número de versión*.</span><span class="sxs-lookup"><span data-stu-id="22650-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="22650-118">Si hay una coincidencia de nombre o GUID y cualquiera de los otros dos elementos es diferente, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="22650-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="22650-119">En caso contrario, si coincide con los tres elementos, `MergeEnd` realiza una comprobación rápida para asegurarse de que las entradas son en realidad duplicados; en caso contrario, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="22650-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="22650-120">Esta comprobación superficial busca:</span><span class="sxs-lookup"><span data-stu-id="22650-120">This cursory check looks for:</span></span>  
  
    -   <span data-ttu-id="22650-121">Las declaraciones de miembro mismo, que se producen en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="22650-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="22650-122">Los miembros que estén marcados como `mdPrivateScope` (consulte la [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeración) no se incluyen en esta comprobación; se combinan de manera especial.</span><span class="sxs-lookup"><span data-stu-id="22650-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>  
  
    -   <span data-ttu-id="22650-123">El mismo diseño de clase.</span><span class="sxs-lookup"><span data-stu-id="22650-123">The same class layout.</span></span>  
  
     <span data-ttu-id="22650-124">Esto significa que un `TypeDef` objeto debe siempre completa y coherente definirse en cada ámbito de metadatos donde se declara; si sus implementaciones de miembros (para una clase) se reparten entre varias unidades de compilación, la definición completa se supone que presentes en cada ámbito y no de forma incremental a cada ámbito.</span><span class="sxs-lookup"><span data-stu-id="22650-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="22650-125">Por ejemplo, si los nombres de parámetro son relevantes para el contrato, se debe emitir la misma manera en cada ámbito; Si no son relevantes, no se emite en metadatos.</span><span class="sxs-lookup"><span data-stu-id="22650-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>  
  
     <span data-ttu-id="22650-126">La excepción es que un `TypeDef` objeto puede tener miembros incrementales marcados como `mdPrivateScope`.</span><span class="sxs-lookup"><span data-stu-id="22650-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="22650-127">Al encontrar estos, `MergeEnd` agrega incrementalmente al ámbito actual sin tener en cuenta para los duplicados.</span><span class="sxs-lookup"><span data-stu-id="22650-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="22650-128">Dado que el compilador reconoce el ámbito privado, el compilador debe ser responsable de aplicar las reglas.</span><span class="sxs-lookup"><span data-stu-id="22650-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>  
  
-   <span data-ttu-id="22650-129">Direcciones virtuales relativas (RVA) no se importan o se combinan; el compilador debe volver a emitir esta información.</span><span class="sxs-lookup"><span data-stu-id="22650-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>  
  
-   <span data-ttu-id="22650-130">Atributos personalizados se combinan solo cuando se combina el elemento al que se adjunta.</span><span class="sxs-lookup"><span data-stu-id="22650-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="22650-131">Por ejemplo, se combinan los atributos personalizados asociados a una clase cuando la clase aparece por primera vez.</span><span class="sxs-lookup"><span data-stu-id="22650-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="22650-132">Si los atributos personalizados están asociados con un `TypeDef` o `MemberDef` que es específico de la unidad de compilación (por ejemplo, la marca de tiempo de una compilación de miembro), no se combinan y se deja al compilador que quitar o actualizar tales metadatos.</span><span class="sxs-lookup"><span data-stu-id="22650-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22650-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22650-133">Requirements</span></span>  
 <span data-ttu-id="22650-134">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22650-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22650-135">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="22650-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22650-136">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="22650-136">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22650-137">**Versiones de .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22650-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22650-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="22650-138">See Also</span></span>  
 [<span data-ttu-id="22650-139">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="22650-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="22650-140">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="22650-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
