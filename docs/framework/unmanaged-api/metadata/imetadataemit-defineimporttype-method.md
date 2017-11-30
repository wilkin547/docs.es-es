---
title: "IMetaDataEmit::DefineImportType (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineImportType
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4b19b291917b0b507f03c66a358b725a29234f76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="c9866-102">IMetaDataEmit::DefineImportType (Método)</span><span class="sxs-lookup"><span data-stu-id="c9866-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="c9866-103">Crea una referencia al tipo especificado que se define fuera del ámbito actual y define un símbolo (token) para esa referencia.</span><span class="sxs-lookup"><span data-stu-id="c9866-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9866-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9866-104">Syntax</span></span>  
  
```  
HRESULT DefineImportType (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,    
    [in]  IMetaDataImport          *pImport,   
    [in]  mdTypeDef                tdImport,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [out] mdTypeRef                *ptr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9866-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c9866-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="c9866-106">[in] Un [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz que representa el ensamblado desde el que se importa el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="c9866-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="c9866-107">[in] Una matriz que contiene el valor hash para el ensamblado especificado por `pAssemImport`.</span><span class="sxs-lookup"><span data-stu-id="c9866-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="c9866-108">[in] Número de bytes en la matriz `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="c9866-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="c9866-109">[in] Un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz que representa el ámbito de metadatos desde el que se importa el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="c9866-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="c9866-110">[in] Un `mdTypeDef` símbolo (token) que especifica el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="c9866-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="c9866-111">[in] Un [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interfaz que representa el ensamblado al que se importa el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="c9866-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="c9866-112">[out] El `mdTypeRef` (token) que se define en el ámbito actual para la referencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="c9866-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9866-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c9866-113">Remarks</span></span>  
 <span data-ttu-id="c9866-114">Antes de llamar a la [DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) método, puede usar el `DefineImportType` método para crear una referencia de tipo, en el ámbito actual, para el miembro de la clase primaria o interfaz primaria.</span><span class="sxs-lookup"><span data-stu-id="c9866-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9866-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9866-115">Requirements</span></span>  
 <span data-ttu-id="c9866-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9866-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9866-117">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c9866-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c9866-118">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c9866-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9866-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9866-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9866-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9866-120">See Also</span></span>  
 [<span data-ttu-id="c9866-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9866-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="c9866-122">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9866-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
