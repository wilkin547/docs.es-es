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
ms.openlocfilehash: a7449ffc8a8ccf2db62ab3cff2f9cfaffd0c72a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175868"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="8496c-102">IMetaDataEmit::DefineImportMember (Método)</span><span class="sxs-lookup"><span data-stu-id="8496c-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="8496c-103">Crea una referencia al miembro especificado de un tipo o módulo que se define fuera del ámbito actual y define un token para esa referencia.</span><span class="sxs-lookup"><span data-stu-id="8496c-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8496c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8496c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8496c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8496c-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="8496c-106">[en] Una interfaz [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) que representa el ensamblado desde el que se importa el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="8496c-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="8496c-107">[en] Matriz que contiene el hash del `pAssemImport`ensamblado especificado por .</span><span class="sxs-lookup"><span data-stu-id="8496c-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="8496c-108">[in] Número de bytes en la matriz `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="8496c-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="8496c-109">[en] Una interfaz [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) que representa el ámbito de metadatos desde el que se importa el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="8496c-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="8496c-110">[en] El token de metadatos que especifica el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="8496c-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="8496c-111">El token puede `mdMethodDef` ser un token `mdProperty` (para un método `mdFieldDef` miembro), (para una propiedad miembro) o (para un campo miembro).</span><span class="sxs-lookup"><span data-stu-id="8496c-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="8496c-112">[en] Una [interfaz IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) que representa el ensamblado en el que se importa el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="8496c-112">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="8496c-113">[en] El `mdTypeRef` `mdModuleRef` token o para el tipo o módulo, respectivamente, que posee el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="8496c-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="8496c-114">[fuera] El `mdMemberRef` token que se define en el ámbito actual para la referencia de miembro.</span><span class="sxs-lookup"><span data-stu-id="8496c-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8496c-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8496c-115">Remarks</span></span>  
 <span data-ttu-id="8496c-116">El `DefineImportMember` método busca el miembro, `mbMember`especificado por , que se `pImport`define en otro ámbito, especificado por , y recupera sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="8496c-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="8496c-117">Usa esta información para llamar a la [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) método en el ámbito actual para crear la referencia de miembro.</span><span class="sxs-lookup"><span data-stu-id="8496c-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="8496c-118">Por lo general, `DefineImportMember` antes de usar el método, debe crear, en el ámbito actual, una referencia de tipo o una referencia de módulo para la clase primaria, la interfaz o el módulo del miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="8496c-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="8496c-119">A continuación, el token de `tkParent` metadatos para esta referencia se pasa en el argumento.</span><span class="sxs-lookup"><span data-stu-id="8496c-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="8496c-120">No es necesario crear una referencia al elemento primario del miembro de destino si el compilador o vinculador la resolverá más adelante.</span><span class="sxs-lookup"><span data-stu-id="8496c-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="8496c-121">Resumiendo:</span><span class="sxs-lookup"><span data-stu-id="8496c-121">To summarize:</span></span>  
  
- <span data-ttu-id="8496c-122">Si el miembro de destino es un campo o método, utilice el [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) o el [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) método para crear una referencia de tipo, en el ámbito actual, para la clase primaria del miembro o la interfaz primaria.</span><span class="sxs-lookup"><span data-stu-id="8496c-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
- <span data-ttu-id="8496c-123">Si el miembro de destino es una variable global o una función global (es decir, no un miembro de una clase o interfaz), utilice el [método IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) para crear una referencia de módulo, en el ámbito actual, para el módulo primario del miembro.</span><span class="sxs-lookup"><span data-stu-id="8496c-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
- <span data-ttu-id="8496c-124">Si el compilador o vinculador resolverá el elemento primario `mdTokenNil` del `tkParent`miembro de destino más adelante, pase .</span><span class="sxs-lookup"><span data-stu-id="8496c-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="8496c-125">El único escenario en el que esto se aplica es cuando una función global o variable global se está importando desde un archivo .obj que, en última instancia, se vinculará al módulo actual y los metadatos se fusionarán.</span><span class="sxs-lookup"><span data-stu-id="8496c-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8496c-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8496c-126">Requirements</span></span>  
 <span data-ttu-id="8496c-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8496c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8496c-128">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8496c-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8496c-129">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8496c-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8496c-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8496c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8496c-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8496c-131">See also</span></span>

- [<span data-ttu-id="8496c-132">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8496c-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8496c-133">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8496c-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
