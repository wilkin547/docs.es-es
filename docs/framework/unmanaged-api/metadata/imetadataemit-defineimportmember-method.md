---
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
ms.openlocfilehash: ec8a24251ac4f0701b1adab19829078270229ced
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004600"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="98074-102">IMetaDataEmit::DefineImportMember (Método)</span><span class="sxs-lookup"><span data-stu-id="98074-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="98074-103">Crea una referencia al miembro especificado de un tipo o módulo que se define fuera del ámbito actual y define un token para esa referencia.</span><span class="sxs-lookup"><span data-stu-id="98074-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98074-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98074-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="98074-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98074-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="98074-106">de Una interfaz [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) que representa el ensamblado desde el que se importa el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="98074-106">[in] An [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="98074-107">de Una matriz que contiene el hash para el ensamblado especificado por `pAssemImport` .</span><span class="sxs-lookup"><span data-stu-id="98074-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="98074-108">[in] Número de bytes en la matriz `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="98074-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="98074-109">de Interfaz [IMetaDataImport](imetadataimport-interface.md) que representa el ámbito de metadatos desde el que se importa el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="98074-109">[in] An [IMetaDataImport](imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="98074-110">de Token de metadatos que especifica el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="98074-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="98074-111">El token puede ser un `mdMethodDef` (para un método de miembro), `mdProperty` (para una propiedad de miembro) o un `mdFieldDef` token (para un campo de miembro).</span><span class="sxs-lookup"><span data-stu-id="98074-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="98074-112">de Una interfaz [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) que representa el ensamblado en el que se importa el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="98074-112">[in] An [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="98074-113">de El `mdTypeRef` `mdModuleRef` token o para el tipo o módulo, respectivamente, que posee el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="98074-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="98074-114">enuncia El `mdMemberRef` token que se define en el ámbito actual para la referencia de miembro.</span><span class="sxs-lookup"><span data-stu-id="98074-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98074-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="98074-115">Remarks</span></span>  
 <span data-ttu-id="98074-116">El `DefineImportMember` método busca el miembro, especificado por `mbMember` , que se define en otro ámbito, especificado por `pImport` , y recupera sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="98074-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="98074-117">Usa esta información para llamar al método [IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md) en el ámbito actual para crear la referencia de miembro.</span><span class="sxs-lookup"><span data-stu-id="98074-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="98074-118">Normalmente, antes de usar el `DefineImportMember` método, debe crear, en el ámbito actual, una referencia de tipo o referencia de módulo para la clase primaria, la interfaz o el módulo del miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="98074-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="98074-119">A continuación, se pasa el token de metadatos para esta referencia en el `tkParent` argumento.</span><span class="sxs-lookup"><span data-stu-id="98074-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="98074-120">No es necesario crear una referencia al elemento primario del miembro de destino si el compilador o el vinculador lo resolverán más adelante.</span><span class="sxs-lookup"><span data-stu-id="98074-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="98074-121">Resumiendo:</span><span class="sxs-lookup"><span data-stu-id="98074-121">To summarize:</span></span>  
  
- <span data-ttu-id="98074-122">Si el miembro de destino es un campo o un método, use el método [IMetaDataEmit::D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) o [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md) para crear una referencia de tipo, en el ámbito actual, para la clase primaria o la interfaz primaria del miembro.</span><span class="sxs-lookup"><span data-stu-id="98074-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
- <span data-ttu-id="98074-123">Si el miembro de destino es una variable global o una función global (es decir, no es un miembro de una clase o interfaz), use el método [IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md) para crear una referencia de módulo, en el ámbito actual, para el módulo primario del miembro.</span><span class="sxs-lookup"><span data-stu-id="98074-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
- <span data-ttu-id="98074-124">Si el elemento primario del miembro de destino se resolverá más adelante mediante el compilador o el vinculador, pase `mdTokenNil` `tkParent` .</span><span class="sxs-lookup"><span data-stu-id="98074-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="98074-125">El único escenario en el que esto se aplica es cuando se importa una función global o una variable global desde un archivo. obj que se vinculará en última instancia al módulo actual y los metadatos combinados.</span><span class="sxs-lookup"><span data-stu-id="98074-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98074-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98074-126">Requirements</span></span>  
 <span data-ttu-id="98074-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98074-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98074-128">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="98074-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="98074-129">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="98074-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98074-130">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98074-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98074-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98074-131">See also</span></span>

- [<span data-ttu-id="98074-132">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="98074-132">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="98074-133">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="98074-133">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
