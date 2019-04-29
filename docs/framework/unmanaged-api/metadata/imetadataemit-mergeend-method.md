---
title: IMetaDataEmit::MergeEnd (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 277e7e57ae01128039c3a280158110acde3363a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944552"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="da8ca-102">IMetaDataEmit::MergeEnd (Método)</span><span class="sxs-lookup"><span data-stu-id="da8ca-102">IMetaDataEmit::MergeEnd Method</span></span>
<span data-ttu-id="da8ca-103">Combina en el actual ámbito de todos los ámbitos de los metadatos especificados por una o varias llamadas anteriores al [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span><span class="sxs-lookup"><span data-stu-id="da8ca-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da8ca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da8ca-104">Syntax</span></span>  
  
```  
HRESULT MergeEnd ();  
```  
  
## <a name="parameters"></a><span data-ttu-id="da8ca-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da8ca-105">Parameters</span></span>  
 <span data-ttu-id="da8ca-106">Este método no toma ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="da8ca-106">This method takes no parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da8ca-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="da8ca-107">Remarks</span></span>  
 <span data-ttu-id="da8ca-108">Esta rutina desencadena la combinación real de los metadatos, de todos los ámbitos especificados utilizando delante de las llamadas a de importación `IMetaDataEmit::Merge`, en el ámbito de salida actual.</span><span class="sxs-lookup"><span data-stu-id="da8ca-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>  
  
 <span data-ttu-id="da8ca-109">Se aplican las siguientes condiciones especiales para la fusión mediante combinación:</span><span class="sxs-lookup"><span data-stu-id="da8ca-109">The following special conditions apply to the merge:</span></span>  
  
- <span data-ttu-id="da8ca-110">Un identificador de versión de módulo (MVID) nunca se importa, porque es único para los metadatos en el ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="da8ca-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>  
  
- <span data-ttu-id="da8ca-111">No hay propiedades de todo el módulo existentes se sobrescriben.</span><span class="sxs-lookup"><span data-stu-id="da8ca-111">No existing module-wide properties are overwritten.</span></span>  
  
     <span data-ttu-id="da8ca-112">Si ya se han establecido propiedades del módulo para el ámbito actual, no hay propiedades del módulo se importan.</span><span class="sxs-lookup"><span data-stu-id="da8ca-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="da8ca-113">Sin embargo, si no se han establecido las propiedades de módulo en el ámbito actual, se importan solo una vez, cuando se encuentran en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="da8ca-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="da8ca-114">Si se vuelven a encontrar las propiedades de módulo, son duplicados.</span><span class="sxs-lookup"><span data-stu-id="da8ca-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="da8ca-115">Si se comparan los valores de todas las propiedades de módulo (excepto el MVID) y no se encuentran duplicados, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="da8ca-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>  
  
- <span data-ttu-id="da8ca-116">Para obtener definiciones de tipo (`TypeDef`), no hay duplicados se combinan en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="da8ca-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="da8ca-117">`TypeDef` se comprueban los objetos duplicados en cada *nombre de objeto completo* + *GUID* + *número de versión*.</span><span class="sxs-lookup"><span data-stu-id="da8ca-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="da8ca-118">Si hay una coincidencia en el nombre o GUID y cualquiera de los otros dos elementos es diferente, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="da8ca-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="da8ca-119">En caso contrario, si coincide con los tres elementos, `MergeEnd` realiza una comprobación rápida para asegurarse de que las entradas son en realidad duplicados; en caso contrario, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="da8ca-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="da8ca-120">Esta comprobación superficial busca:</span><span class="sxs-lookup"><span data-stu-id="da8ca-120">This cursory check looks for:</span></span>  
  
    - <span data-ttu-id="da8ca-121">Las declaraciones de miembro mismo, que se producen en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="da8ca-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="da8ca-122">Los miembros que se marcan como `mdPrivateScope` (consulte la [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeración) no se incluyen en esta comprobación; se combinan de manera especial.</span><span class="sxs-lookup"><span data-stu-id="da8ca-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>  
  
    - <span data-ttu-id="da8ca-123">El mismo diseño de clase.</span><span class="sxs-lookup"><span data-stu-id="da8ca-123">The same class layout.</span></span>  
  
     <span data-ttu-id="da8ca-124">Esto significa que un `TypeDef` objeto debe siempre por completo y coherente definirse en cada ámbito de metadatos donde se declara; si sus implementaciones de miembros (para una clase) se reparten entre varias unidades de compilación, la definición completa se supone que presente en cada ámbito y no es incremental para cada ámbito.</span><span class="sxs-lookup"><span data-stu-id="da8ca-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="da8ca-125">Por ejemplo, si los nombres de parámetro son relevantes para el contrato, se debe emitir la misma manera en cada ámbito; Si no son relevantes, no se emiten en metadatos.</span><span class="sxs-lookup"><span data-stu-id="da8ca-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>  
  
     <span data-ttu-id="da8ca-126">La excepción es que un `TypeDef` objeto puede tener miembros incrementales marcados como `mdPrivateScope`.</span><span class="sxs-lookup"><span data-stu-id="da8ca-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="da8ca-127">Al encontrar estos, `MergeEnd` agrega incrementalmente el ámbito actual sin tener en cuenta los duplicados.</span><span class="sxs-lookup"><span data-stu-id="da8ca-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="da8ca-128">Dado que el compilador reconoce el ámbito privado, el compilador debe ser responsable de aplicar las reglas.</span><span class="sxs-lookup"><span data-stu-id="da8ca-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>  
  
- <span data-ttu-id="da8ca-129">No se importan o se combinan; direcciones virtuales relativas (RVA) el compilador se espera volver a emitir esta información.</span><span class="sxs-lookup"><span data-stu-id="da8ca-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>  
  
- <span data-ttu-id="da8ca-130">Se combinan los atributos personalizados solo cuando se combina el elemento al que están conectados.</span><span class="sxs-lookup"><span data-stu-id="da8ca-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="da8ca-131">Por ejemplo, se combinan los atributos personalizados asociados a una clase cuando la clase se encuentra en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="da8ca-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="da8ca-132">Si los atributos personalizados que están asociados con un `TypeDef` o `MemberDef` específica de la unidad de compilación (por ejemplo, la marca de tiempo de compilación de un miembro), no se combinan y se deja al compilador que quitar o actualizar estos metadatos.</span><span class="sxs-lookup"><span data-stu-id="da8ca-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da8ca-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da8ca-133">Requirements</span></span>  
 <span data-ttu-id="da8ca-134">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da8ca-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da8ca-135">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="da8ca-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da8ca-136">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da8ca-136">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da8ca-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da8ca-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da8ca-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="da8ca-138">See also</span></span>

- [<span data-ttu-id="da8ca-139">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="da8ca-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="da8ca-140">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="da8ca-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
