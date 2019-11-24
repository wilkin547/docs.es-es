---
title: IMetaDataEmit::SetTypeDefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: 3ab29fc8c983b354ad5088d26c547868940ec70a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447720"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="10a8e-102">IMetaDataEmit::SetTypeDefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="10a8e-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="10a8e-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="10a8e-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10a8e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10a8e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10a8e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10a8e-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="10a8e-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="10a8e-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="10a8e-107">[in] `TypeDef` attributes.</span><span class="sxs-lookup"><span data-stu-id="10a8e-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="10a8e-108">This is a bitmask of `CorTypeAttr` values.</span><span class="sxs-lookup"><span data-stu-id="10a8e-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="10a8e-109">[in] The `mdToken` of the base class.</span><span class="sxs-lookup"><span data-stu-id="10a8e-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="10a8e-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span><span class="sxs-lookup"><span data-stu-id="10a8e-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="10a8e-111">[in] An array of tokens for the interfaces that this type implements.</span><span class="sxs-lookup"><span data-stu-id="10a8e-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="10a8e-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="10a8e-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="10a8e-113">The last element of the array is must be `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="10a8e-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10a8e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10a8e-114">Requirements</span></span>  
 <span data-ttu-id="10a8e-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10a8e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10a8e-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="10a8e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="10a8e-117">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10a8e-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10a8e-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10a8e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a8e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="10a8e-119">See also</span></span>

- [<span data-ttu-id="10a8e-120">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="10a8e-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="10a8e-121">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="10a8e-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
