---
title: "IMetaDataEmit::DefineNestedType (Método)"
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
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99250d98f9ffd90857128aa5d8a675a997926bf5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="88434-102">IMetaDataEmit::DefineNestedType (Método)</span><span class="sxs-lookup"><span data-stu-id="88434-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="88434-103">Crea la firma de metadatos de una definición de tipo, se devuelve un `mdTypeDef` de token de ese tipo y especifica que el tipo definido es un miembro del tipo al que hace referencia el `tdEncloser` parámetro.</span><span class="sxs-lookup"><span data-stu-id="88434-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88434-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88434-104">Syntax</span></span>  
  
```  
HRESULT DefineNestedType (   
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [in]  mdTypeDef   tdEncloser,   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88434-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="88434-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="88434-106">[in] El nombre del tipo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="88434-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="88434-107">[in] `TypeDef` atributos.</span><span class="sxs-lookup"><span data-stu-id="88434-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="88434-108">Se trata de una máscara de bits de `CorTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="88434-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="88434-109">[in] El token de la clase base.</span><span class="sxs-lookup"><span data-stu-id="88434-109">[in] The token of the base class.</span></span> <span data-ttu-id="88434-110">Esto es un `mdTypeDef` o un `mdTypeRef` símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="88434-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="88434-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="88434-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="88434-112">[in] Una matriz de símbolos (tokens) que especifican las interfaces que implementa esta interfaz o clase.</span><span class="sxs-lookup"><span data-stu-id="88434-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="88434-113">[in] El token del tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="88434-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="88434-114">El último elemento de la matriz debe ser `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="88434-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="88434-115">[out] El `mdTypeDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="88434-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88434-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88434-116">Requirements</span></span>  
 <span data-ttu-id="88434-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88434-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88434-118">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="88434-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="88434-119">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="88434-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88434-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88434-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88434-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="88434-121">See Also</span></span>  
 [<span data-ttu-id="88434-122">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="88434-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="88434-123">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="88434-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
