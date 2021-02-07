---
description: 'Más información sobre: IMetaDataEmit:: Mergeend ((método)'
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
ms.openlocfilehash: aac48b9bafb60cee4e3d73232d9f9c00cca7f796
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745884"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="0adf7-103">IMetaDataEmit::MergeEnd (Método)</span><span class="sxs-lookup"><span data-stu-id="0adf7-103">IMetaDataEmit::MergeEnd Method</span></span>

<span data-ttu-id="0adf7-104">Combina en el ámbito actual todos los ámbitos de metadatos especificados por una o varias llamadas anteriores a [IMetaDataEmit:: Merge](imetadataemit-merge-method.md).</span><span class="sxs-lookup"><span data-stu-id="0adf7-104">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](imetadataemit-merge-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="0adf7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0adf7-105">Syntax</span></span>

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a><span data-ttu-id="0adf7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0adf7-106">Parameters</span></span>

<span data-ttu-id="0adf7-107">Este método no toma ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="0adf7-107">This method takes no parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="0adf7-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0adf7-108">Remarks</span></span>

<span data-ttu-id="0adf7-109">Esta rutina desencadena la combinación real de metadatos, de todos los ámbitos de importación especificados por las llamadas anteriores a `IMetaDataEmit::Merge` , en el ámbito de salida actual.</span><span class="sxs-lookup"><span data-stu-id="0adf7-109">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>

<span data-ttu-id="0adf7-110">Las condiciones especiales siguientes se aplican a la combinación:</span><span class="sxs-lookup"><span data-stu-id="0adf7-110">The following special conditions apply to the merge:</span></span>

- <span data-ttu-id="0adf7-111">Un identificador de versión de módulo (MVID) nunca se importa porque es único en los metadatos del ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="0adf7-111">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>

- <span data-ttu-id="0adf7-112">No se sobrescriben las propiedades de todo el módulo.</span><span class="sxs-lookup"><span data-stu-id="0adf7-112">No existing module-wide properties are overwritten.</span></span>

  <span data-ttu-id="0adf7-113">Si ya se han establecido las propiedades del módulo para el ámbito actual, no se importa ninguna propiedad del módulo.</span><span class="sxs-lookup"><span data-stu-id="0adf7-113">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="0adf7-114">Sin embargo, si no se han establecido las propiedades del módulo en el ámbito actual, se importan solo una vez, cuando se encuentran por primera vez.</span><span class="sxs-lookup"><span data-stu-id="0adf7-114">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="0adf7-115">Si las propiedades del módulo se encuentran de nuevo, son duplicados.</span><span class="sxs-lookup"><span data-stu-id="0adf7-115">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="0adf7-116">Si se comparan los valores de todas las propiedades del módulo (excepto MVID) y no se encuentra ningún duplicado, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="0adf7-116">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>

- <span data-ttu-id="0adf7-117">En las definiciones de tipo ( `TypeDef` ), no se combina ningún duplicado en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="0adf7-117">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="0adf7-118">`TypeDef`los objetos se comprueban en busca de duplicados en cada número de versión del GUID del *nombre de objeto completo*  +    +  .</span><span class="sxs-lookup"><span data-stu-id="0adf7-118">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="0adf7-119">Si hay una coincidencia en el nombre o el GUID, y cualquiera de los otros dos elementos es diferente, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="0adf7-119">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="0adf7-120">De lo contrario, si los tres elementos coinciden, `MergeEnd` realiza una comprobación de cursor para asegurarse de que las entradas son realmente duplicados; si no es así, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="0adf7-120">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="0adf7-121">Esta comprobación de cursor busca:</span><span class="sxs-lookup"><span data-stu-id="0adf7-121">This cursory check looks for:</span></span>

  - <span data-ttu-id="0adf7-122">Las mismas declaraciones de miembros, que se producen en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="0adf7-122">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="0adf7-123">Los miembros que se marcan como `mdPrivateScope` (vea la enumeración [cormethodattr (](cormethodattr-enumeration.md) ) no se incluyen en esta comprobación; se combinan de forma especial.</span><span class="sxs-lookup"><span data-stu-id="0adf7-123">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>

  - <span data-ttu-id="0adf7-124">El mismo diseño de clase.</span><span class="sxs-lookup"><span data-stu-id="0adf7-124">The same class layout.</span></span>

  <span data-ttu-id="0adf7-125">Esto significa que un `TypeDef` objeto siempre debe estar definido de forma completa y coherente en cada ámbito de metadatos en el que se declara; si sus implementaciones de miembro (para una clase) se distribuyen entre varias unidades de compilación, se supone que la definición completa está presente en todos los ámbitos y no incremental en cada ámbito.</span><span class="sxs-lookup"><span data-stu-id="0adf7-125">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="0adf7-126">Por ejemplo, si los nombres de parámetro son relevantes para el contrato, deben emitirse de la misma manera en todos los ámbitos; Si no son relevantes, no se deben emitir en metadatos.</span><span class="sxs-lookup"><span data-stu-id="0adf7-126">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>

  <span data-ttu-id="0adf7-127">La excepción es que un `TypeDef` objeto puede tener miembros incrementales marcados como `mdPrivateScope` .</span><span class="sxs-lookup"><span data-stu-id="0adf7-127">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="0adf7-128">Al encontrarlos, `MergeEnd` los agrega incrementalmente al ámbito actual sin tener en cuenta los duplicados.</span><span class="sxs-lookup"><span data-stu-id="0adf7-128">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="0adf7-129">Dado que el compilador entiende el ámbito privado, el compilador debe ser responsable de aplicar las reglas.</span><span class="sxs-lookup"><span data-stu-id="0adf7-129">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>

- <span data-ttu-id="0adf7-130">Las direcciones virtuales relativas (RVA) no se importan ni se combinan; se espera que el compilador vuelva a emitir esta información.</span><span class="sxs-lookup"><span data-stu-id="0adf7-130">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>

- <span data-ttu-id="0adf7-131">Los atributos personalizados solo se combinan cuando se combina el elemento al que están adjuntos.</span><span class="sxs-lookup"><span data-stu-id="0adf7-131">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="0adf7-132">Por ejemplo, los atributos personalizados asociados a una clase se combinan cuando la clase se encuentra por primera vez.</span><span class="sxs-lookup"><span data-stu-id="0adf7-132">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="0adf7-133">Si los atributos personalizados están asociados a un objeto `TypeDef` o `MemberDef` que es específico de la unidad de compilación (por ejemplo, la marca de tiempo de una compilación de miembro), no se combinan y depende del compilador quitar o actualizar dichos metadatos.</span><span class="sxs-lookup"><span data-stu-id="0adf7-133">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="0adf7-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0adf7-134">Requirements</span></span>

<span data-ttu-id="0adf7-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0adf7-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="0adf7-136">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0adf7-136">**Header:** Cor.h</span></span>

<span data-ttu-id="0adf7-137">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0adf7-137">**Library:** Used as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="0adf7-138">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0adf7-138">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0adf7-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="0adf7-139">See also</span></span>

- [<span data-ttu-id="0adf7-140">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0adf7-140">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="0adf7-141">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0adf7-141">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
