---
description: 'Más información acerca de: IMetaDataEmit::D método efineImportMember'
title: IMetaDataEmit::DefineImportMember (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
ms.openlocfilehash: 91c6ea70d38b8d4f73570ed19d86bacca30ebae5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753463"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="44c4d-103">IMetaDataEmit::DefineImportMember (Método)</span><span class="sxs-lookup"><span data-stu-id="44c4d-103">IMetaDataEmit::DefineImportMember Method</span></span>

<span data-ttu-id="44c4d-104">Crea una referencia al miembro especificado de un tipo o módulo que se define fuera del ámbito actual y define un token para esa referencia.</span><span class="sxs-lookup"><span data-stu-id="44c4d-104">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44c4d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44c4d-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineImportMember (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,
    [in]  mdToken                  mbMember,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [in]  mdToken                  tkParent,
    [out] mdMemberRef              *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44c4d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44c4d-106">Parameters</span></span>  

 `pAssemImport`  
 <span data-ttu-id="44c4d-107">de Una interfaz [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) que representa el ensamblado desde el que se importa el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="44c4d-107">[in] An [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="44c4d-108">de Una matriz que contiene el hash para el ensamblado especificado por `pAssemImport` .</span><span class="sxs-lookup"><span data-stu-id="44c4d-108">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="44c4d-109">[in] Número de bytes en la matriz `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="44c4d-109">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="44c4d-110">de Interfaz [IMetaDataImport](imetadataimport-interface.md) que representa el ámbito de metadatos desde el que se importa el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="44c4d-110">[in] An [IMetaDataImport](imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="44c4d-111">de Token de metadatos que especifica el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="44c4d-111">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="44c4d-112">El token puede ser un `mdMethodDef` (para un método de miembro), `mdProperty` (para una propiedad de miembro) o un `mdFieldDef` token (para un campo de miembro).</span><span class="sxs-lookup"><span data-stu-id="44c4d-112">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="44c4d-113">de Una interfaz [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) que representa el ensamblado en el que se importa el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="44c4d-113">[in] An [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="44c4d-114">de El `mdTypeRef` `mdModuleRef` token o para el tipo o módulo, respectivamente, que posee el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="44c4d-114">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="44c4d-115">enuncia El `mdMemberRef` token que se define en el ámbito actual para la referencia de miembro.</span><span class="sxs-lookup"><span data-stu-id="44c4d-115">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44c4d-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="44c4d-116">Remarks</span></span>  

 <span data-ttu-id="44c4d-117">El `DefineImportMember` método busca el miembro, especificado por `mbMember` , que se define en otro ámbito, especificado por `pImport` , y recupera sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="44c4d-117">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="44c4d-118">Usa esta información para llamar al método [IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md) en el ámbito actual para crear la referencia de miembro.</span><span class="sxs-lookup"><span data-stu-id="44c4d-118">It uses this information to call the [IMetaDataEmit::DefineMemberRef](imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="44c4d-119">Normalmente, antes de usar el `DefineImportMember` método, debe crear, en el ámbito actual, una referencia de tipo o referencia de módulo para la clase primaria, la interfaz o el módulo del miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="44c4d-119">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="44c4d-120">A continuación, se pasa el token de metadatos para esta referencia en el `tkParent` argumento.</span><span class="sxs-lookup"><span data-stu-id="44c4d-120">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="44c4d-121">No es necesario crear una referencia al elemento primario del miembro de destino si el compilador o el vinculador lo resolverán más adelante.</span><span class="sxs-lookup"><span data-stu-id="44c4d-121">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="44c4d-122">En resumen:</span><span class="sxs-lookup"><span data-stu-id="44c4d-122">To summarize:</span></span>  
  
- <span data-ttu-id="44c4d-123">Si el miembro de destino es un campo o un método, use el método [IMetaDataEmit::D efinetyperefbyname](imetadataemit-definetyperefbyname-method.md) o [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md) para crear una referencia de tipo, en el ámbito actual, para la clase primaria o la interfaz primaria del miembro.</span><span class="sxs-lookup"><span data-stu-id="44c4d-123">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
- <span data-ttu-id="44c4d-124">Si el miembro de destino es una variable global o una función global (es decir, no es un miembro de una clase o interfaz), use el método [IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md) para crear una referencia de módulo, en el ámbito actual, para el módulo primario del miembro.</span><span class="sxs-lookup"><span data-stu-id="44c4d-124">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
- <span data-ttu-id="44c4d-125">Si el elemento primario del miembro de destino se resolverá más adelante mediante el compilador o el vinculador, pase `mdTokenNil` `tkParent` .</span><span class="sxs-lookup"><span data-stu-id="44c4d-125">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="44c4d-126">El único escenario en el que esto se aplica es cuando se importa una función global o una variable global desde un archivo. obj que se vinculará en última instancia al módulo actual y los metadatos combinados.</span><span class="sxs-lookup"><span data-stu-id="44c4d-126">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44c4d-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44c4d-127">Requirements</span></span>  

 <span data-ttu-id="44c4d-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44c4d-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44c4d-129">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="44c4d-129">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44c4d-130">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="44c4d-130">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44c4d-131">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44c4d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c4d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="44c4d-132">See also</span></span>

- [<span data-ttu-id="44c4d-133">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44c4d-133">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="44c4d-134">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44c4d-134">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
