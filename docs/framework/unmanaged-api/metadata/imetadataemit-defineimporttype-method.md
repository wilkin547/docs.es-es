---
title: IMetaDataEmit::DefineImportType (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff0660ef2b30e32af540fe7bef5936ab6d0a359f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777631"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="2e466-102">IMetaDataEmit::DefineImportType (Método)</span><span class="sxs-lookup"><span data-stu-id="2e466-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="2e466-103">Crea una referencia al tipo especificado que se define fuera del ámbito actual y define un token para esa referencia.</span><span class="sxs-lookup"><span data-stu-id="2e466-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e466-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e466-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="2e466-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2e466-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="2e466-106">[in] Un [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz que representa el ensamblado del que se importa el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="2e466-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="2e466-107">[in] Una matriz que contiene el valor hash para el ensamblado especificado por `pAssemImport`.</span><span class="sxs-lookup"><span data-stu-id="2e466-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="2e466-108">[in] Número de bytes en la matriz `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="2e466-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="2e466-109">[in] Un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz que representa el ámbito de metadatos desde el que se importa el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="2e466-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="2e466-110">[in] Un `mdTypeDef` símbolo (token) que especifica el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="2e466-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="2e466-111">[in] Un [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interfaz que representa el ensamblado al que se importa el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="2e466-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="2e466-112">[out] El `mdTypeRef` símbolo (token) que se define en el ámbito actual para la referencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="2e466-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e466-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2e466-113">Remarks</span></span>  
 <span data-ttu-id="2e466-114">Antes de llamar a la [DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) método, puede usar el `DefineImportType` método para crear una referencia de tipo, en el ámbito actual, para la clase primaria o la interfaz primaria del miembro.</span><span class="sxs-lookup"><span data-stu-id="2e466-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e466-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e466-115">Requirements</span></span>  
 <span data-ttu-id="2e466-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e466-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e466-117">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="2e466-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2e466-118">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2e466-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e466-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e466-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e466-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e466-120">See also</span></span>

- [<span data-ttu-id="2e466-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e466-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2e466-122">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e466-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
