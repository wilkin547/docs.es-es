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
ms.openlocfilehash: feb81b86190f953b50f43f244f4e58a0a482f86e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003924"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="e0148-102">IMetaDataEmit::MergeEnd (Método)</span><span class="sxs-lookup"><span data-stu-id="e0148-102">IMetaDataEmit::MergeEnd Method</span></span>

<span data-ttu-id="e0148-103">Combina en el ámbito actual todos los ámbitos de metadatos especificados por una o varias llamadas anteriores a [IMetaDataEmit:: Merge](imetadataemit-merge-method.md).</span><span class="sxs-lookup"><span data-stu-id="e0148-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](imetadataemit-merge-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="e0148-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0148-104">Syntax</span></span>

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a><span data-ttu-id="e0148-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0148-105">Parameters</span></span>

<span data-ttu-id="e0148-106">Este método no toma ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="e0148-106">This method takes no parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="e0148-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0148-107">Remarks</span></span>

<span data-ttu-id="e0148-108">Esta rutina desencadena la combinación real de metadatos, de todos los ámbitos de importación especificados por las llamadas anteriores a `IMetaDataEmit::Merge` , en el ámbito de salida actual.</span><span class="sxs-lookup"><span data-stu-id="e0148-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>

<span data-ttu-id="e0148-109">Las condiciones especiales siguientes se aplican a la combinación:</span><span class="sxs-lookup"><span data-stu-id="e0148-109">The following special conditions apply to the merge:</span></span>

- <span data-ttu-id="e0148-110">Un identificador de versión de módulo (MVID) nunca se importa porque es único en los metadatos del ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="e0148-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>

- <span data-ttu-id="e0148-111">No se sobrescriben las propiedades de todo el módulo.</span><span class="sxs-lookup"><span data-stu-id="e0148-111">No existing module-wide properties are overwritten.</span></span>

  <span data-ttu-id="e0148-112">Si ya se han establecido las propiedades del módulo para el ámbito actual, no se importa ninguna propiedad del módulo.</span><span class="sxs-lookup"><span data-stu-id="e0148-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="e0148-113">Sin embargo, si no se han establecido las propiedades del módulo en el ámbito actual, se importan solo una vez, cuando se encuentran por primera vez.</span><span class="sxs-lookup"><span data-stu-id="e0148-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="e0148-114">Si las propiedades del módulo se encuentran de nuevo, son duplicados.</span><span class="sxs-lookup"><span data-stu-id="e0148-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="e0148-115">Si se comparan los valores de todas las propiedades del módulo (excepto MVID) y no se encuentra ningún duplicado, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="e0148-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>

- <span data-ttu-id="e0148-116">En las definiciones de tipo ( `TypeDef` ), no se combina ningún duplicado en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="e0148-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="e0148-117">`TypeDef`los objetos se comprueban en busca de duplicados en cada número de versión del GUID del *nombre de objeto completo*  +  *GUID*  +  *version number*.</span><span class="sxs-lookup"><span data-stu-id="e0148-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="e0148-118">Si hay una coincidencia en el nombre o el GUID, y cualquiera de los otros dos elementos es diferente, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="e0148-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="e0148-119">De lo contrario, si los tres elementos coinciden, `MergeEnd` realiza una comprobación de cursor para asegurarse de que las entradas son realmente duplicados; si no es así, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="e0148-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="e0148-120">Esta comprobación de cursor busca:</span><span class="sxs-lookup"><span data-stu-id="e0148-120">This cursory check looks for:</span></span>

  - <span data-ttu-id="e0148-121">Las mismas declaraciones de miembros, que se producen en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="e0148-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="e0148-122">Los miembros que se marcan como `mdPrivateScope` (vea la enumeración [cormethodattr (](cormethodattr-enumeration.md) ) no se incluyen en esta comprobación; se combinan de forma especial.</span><span class="sxs-lookup"><span data-stu-id="e0148-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>

  - <span data-ttu-id="e0148-123">El mismo diseño de clase.</span><span class="sxs-lookup"><span data-stu-id="e0148-123">The same class layout.</span></span>

  <span data-ttu-id="e0148-124">Esto significa que un `TypeDef` objeto siempre debe estar definido de forma completa y coherente en cada ámbito de metadatos en el que se declara; si sus implementaciones de miembro (para una clase) se distribuyen entre varias unidades de compilación, se supone que la definición completa está presente en todos los ámbitos y no incremental en cada ámbito.</span><span class="sxs-lookup"><span data-stu-id="e0148-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="e0148-125">Por ejemplo, si los nombres de parámetro son relevantes para el contrato, deben emitirse de la misma manera en todos los ámbitos; Si no son relevantes, no se deben emitir en metadatos.</span><span class="sxs-lookup"><span data-stu-id="e0148-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>

  <span data-ttu-id="e0148-126">La excepción es que un `TypeDef` objeto puede tener miembros incrementales marcados como `mdPrivateScope` .</span><span class="sxs-lookup"><span data-stu-id="e0148-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="e0148-127">Al encontrarlos, `MergeEnd` los agrega incrementalmente al ámbito actual sin tener en cuenta los duplicados.</span><span class="sxs-lookup"><span data-stu-id="e0148-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="e0148-128">Dado que el compilador entiende el ámbito privado, el compilador debe ser responsable de aplicar las reglas.</span><span class="sxs-lookup"><span data-stu-id="e0148-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>

- <span data-ttu-id="e0148-129">Las direcciones virtuales relativas (RVA) no se importan ni se combinan; se espera que el compilador vuelva a emitir esta información.</span><span class="sxs-lookup"><span data-stu-id="e0148-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>

- <span data-ttu-id="e0148-130">Los atributos personalizados solo se combinan cuando se combina el elemento al que están adjuntos.</span><span class="sxs-lookup"><span data-stu-id="e0148-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="e0148-131">Por ejemplo, los atributos personalizados asociados a una clase se combinan cuando la clase se encuentra por primera vez.</span><span class="sxs-lookup"><span data-stu-id="e0148-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="e0148-132">Si los atributos personalizados están asociados a un objeto `TypeDef` o `MemberDef` que es específico de la unidad de compilación (por ejemplo, la marca de tiempo de una compilación de miembro), no se combinan y depende del compilador quitar o actualizar dichos metadatos.</span><span class="sxs-lookup"><span data-stu-id="e0148-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="e0148-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0148-133">Requirements</span></span>

<span data-ttu-id="e0148-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0148-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="e0148-135">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e0148-135">**Header:** Cor.h</span></span>

<span data-ttu-id="e0148-136">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e0148-136">**Library:** Used as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="e0148-137">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0148-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e0148-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0148-138">See also</span></span>

- [<span data-ttu-id="e0148-139">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0148-139">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e0148-140">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0148-140">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
