---
title: IMetaDataEmit::SetPropertyProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
ms.openlocfilehash: 0fdec87324d6efa0f911e37573093c19b93c0349
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440539"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="a7300-102">IMetaDataEmit::SetPropertyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="a7300-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="a7300-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span><span class="sxs-lookup"><span data-stu-id="a7300-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7300-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7300-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertyProps (   
    [in]  mdProperty      pr,   
    [in]  DWORD           dwPropFlags,   
    [in]  DWORD           dwCPlusTypeFlag,   
    [in]  void const      *pValue,   
    [in]  ULONG           cchValue,   
    [in]  mdMethodDef     mdSetter,   
    [in]  mdMethodDef     mdGetter,   
    [in]  mdMethodDef     rmdOtherMethods[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7300-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7300-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="a7300-106">[in] The token for the property to be changed</span><span class="sxs-lookup"><span data-stu-id="a7300-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="a7300-107">[in] Property flags.</span><span class="sxs-lookup"><span data-stu-id="a7300-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="a7300-108">[in] The type of the property's default value.</span><span class="sxs-lookup"><span data-stu-id="a7300-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="a7300-109">[in] The default value for the property.</span><span class="sxs-lookup"><span data-stu-id="a7300-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="a7300-110">[in] The count of (Unicode) characters in `pValue`.</span><span class="sxs-lookup"><span data-stu-id="a7300-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="a7300-111">[in] The method that sets the property value.</span><span class="sxs-lookup"><span data-stu-id="a7300-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="a7300-112">[in] The method that gets the property value.</span><span class="sxs-lookup"><span data-stu-id="a7300-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="a7300-113">[in] An array of other methods associated with the property.</span><span class="sxs-lookup"><span data-stu-id="a7300-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="a7300-114">Terminate this array with an `mdTokenNil` token.</span><span class="sxs-lookup"><span data-stu-id="a7300-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7300-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7300-115">Requirements</span></span>  
 <span data-ttu-id="a7300-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7300-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7300-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a7300-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7300-118">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7300-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7300-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7300-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7300-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7300-120">See also</span></span>

- [<span data-ttu-id="a7300-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7300-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a7300-122">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7300-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
