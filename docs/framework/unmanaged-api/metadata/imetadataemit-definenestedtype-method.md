---
title: IMetaDataEmit::DefineNestedType (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 3b8fd9876563bace52a6088747d1ca4ed26ea872
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175816"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="300c4-102">IMetaDataEmit::DefineNestedType (Método)</span><span class="sxs-lookup"><span data-stu-id="300c4-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="300c4-103">Crea la firma de metadatos de `mdTypeDef` una definición de tipo, devuelve un token para ese `tdEncloser` tipo y especifica que el tipo definido es un miembro del tipo al que hace referencia el parámetro.</span><span class="sxs-lookup"><span data-stu-id="300c4-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="300c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="300c4-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="300c4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="300c4-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="300c4-106">[en] El nombre del tipo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="300c4-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="300c4-107">[en] `TypeDef` atributos.</span><span class="sxs-lookup"><span data-stu-id="300c4-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="300c4-108">Esta es una `CorTypeAttr` máscara de bits de valores.</span><span class="sxs-lookup"><span data-stu-id="300c4-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="300c4-109">[en] El token de la clase base.</span><span class="sxs-lookup"><span data-stu-id="300c4-109">[in] The token of the base class.</span></span> <span data-ttu-id="300c4-110">Esto es `mdTypeDef` un `mdTypeRef` token o un token.</span><span class="sxs-lookup"><span data-stu-id="300c4-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="300c4-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="300c4-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="300c4-112">[en] Matriz de tokens que especifican las interfaces que implementa esta clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="300c4-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="300c4-113">[en] El token del tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="300c4-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="300c4-114">El último elemento de `mdTokenNil`la matriz debe ser .</span><span class="sxs-lookup"><span data-stu-id="300c4-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="300c4-115">[fuera] El `mdTypeDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="300c4-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="300c4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="300c4-116">Requirements</span></span>  
 <span data-ttu-id="300c4-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="300c4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="300c4-118">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="300c4-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="300c4-119">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="300c4-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="300c4-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="300c4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="300c4-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="300c4-121">See also</span></span>

- [<span data-ttu-id="300c4-122">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="300c4-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="300c4-123">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="300c4-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
