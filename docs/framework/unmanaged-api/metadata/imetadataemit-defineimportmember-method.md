---
title: "IMetaDataEmit::DefineImportMember (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineImportMember
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1bbe2c3144372ba66a0b3bad6198aefeeb7e12d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="46abc-102">IMetaDataEmit::DefineImportMember (Método)</span><span class="sxs-lookup"><span data-stu-id="46abc-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="46abc-103">Crea una referencia al miembro especificado de un tipo o módulo que se define fuera del ámbito actual y define un símbolo (token) para esa referencia.</span><span class="sxs-lookup"><span data-stu-id="46abc-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46abc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46abc-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="46abc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="46abc-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="46abc-106">[in] Un [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz que representa el ensamblado desde el que se importa el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="46abc-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="46abc-107">[in] Una matriz que contiene el valor hash para el ensamblado especificado por `pAssemImport`.</span><span class="sxs-lookup"><span data-stu-id="46abc-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="46abc-108">[in] Número de bytes en la matriz `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="46abc-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="46abc-109">[in] Un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz que representa el ámbito de metadatos desde el que se importa el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="46abc-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="46abc-110">[in] El token de metadatos que especifica al miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="46abc-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="46abc-111">El token puede ser un `mdMethodDef` (para un método de miembro), `mdProperty` (para una propiedad de miembro), o `mdFieldDef` (para un campo de miembro) símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="46abc-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="46abc-112">[in] Un [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interfaz que representa el ensamblado al que se importa el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="46abc-112">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="46abc-113">[in] El `mdTypeRef` o `mdModuleRef` símbolo (token) para el tipo o módulo, respectivamente, que posee el miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="46abc-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="46abc-114">[out] El `mdMemberRef` (token) que se define en el ámbito actual para la referencia de miembro.</span><span class="sxs-lookup"><span data-stu-id="46abc-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46abc-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46abc-115">Remarks</span></span>  
 <span data-ttu-id="46abc-116">El `DefineImportMember` método busca el miembro, especificado por `mbMember`, que se define en otro ámbito, especificado por `pImport`y recupera sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="46abc-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="46abc-117">Esta información se utiliza para llamar a la [IMetaDataEmit:: DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) método en el ámbito actual que se va a crear la referencia de miembro.</span><span class="sxs-lookup"><span data-stu-id="46abc-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="46abc-118">Por lo general, antes de utilizar el `DefineImportMember` método, debe crear, en el ámbito actual, una referencia de tipo o la referencia de módulo para el módulo, interfaz o clase primaria del miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="46abc-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="46abc-119">El token de metadatos para esta referencia se pasa a continuación, en la `tkParent` argumento.</span><span class="sxs-lookup"><span data-stu-id="46abc-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="46abc-120">No es necesario crear una referencia al elemento primario del miembro de destino si se resolverán más tarde mediante el compilador o el vinculador.</span><span class="sxs-lookup"><span data-stu-id="46abc-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="46abc-121">En resumen:</span><span class="sxs-lookup"><span data-stu-id="46abc-121">To summarize:</span></span>  
  
-   <span data-ttu-id="46abc-122">Si el miembro de destino es un campo o método, use la [IMetaDataEmit:: DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) o [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) método para crear una referencia de tipo, en el ámbito actual, para el interfaz primaria o clase primaria del miembro.</span><span class="sxs-lookup"><span data-stu-id="46abc-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
-   <span data-ttu-id="46abc-123">Si el miembro de destino es una función global o variable global (es decir, no un miembro de una clase o interfaz), use la [IMetaDataEmit:: DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) método para crear una referencia al módulo, en el ámbito actual, para el elemento primario del miembro módulo.</span><span class="sxs-lookup"><span data-stu-id="46abc-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
-   <span data-ttu-id="46abc-124">Si se puede resolver el elemento primario del miembro de destino más adelante mediante el compilador o el vinculador, a continuación, pasar `mdTokenNil` en `tkParent`.</span><span class="sxs-lookup"><span data-stu-id="46abc-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="46abc-125">El único escenario en el que se aplica esto es cuando una función global o variable global se va a importar desde un archivo .obj que se vinculará, en última instancia, en el módulo actual y la combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="46abc-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46abc-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46abc-126">Requirements</span></span>  
 <span data-ttu-id="46abc-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46abc-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46abc-128">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="46abc-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="46abc-129">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="46abc-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46abc-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46abc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46abc-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="46abc-131">See Also</span></span>  
 [<span data-ttu-id="46abc-132">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46abc-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="46abc-133">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46abc-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
