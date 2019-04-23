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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdee8491b22675fb8dd8fa89e77ebf8541185173
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207902"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="e9130-102">IMetaDataEmit::SetPropertyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="e9130-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="e9130-103">Establece las características que se almacenan en los metadatos para una propiedad definida por una llamada anterior a [DefineProperty (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span><span class="sxs-lookup"><span data-stu-id="e9130-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9130-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9130-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="e9130-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9130-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="e9130-106">[in] El token que se puede cambiar la propiedad</span><span class="sxs-lookup"><span data-stu-id="e9130-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="e9130-107">[in] Marcas de propiedad.</span><span class="sxs-lookup"><span data-stu-id="e9130-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="e9130-108">[in] El tipo de valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e9130-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="e9130-109">[in] El valor predeterminado para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e9130-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="e9130-110">[in] El recuento de (Unicode) los caracteres de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="e9130-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="e9130-111">[in] El método que establece el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="e9130-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="e9130-112">[in] El método que obtiene el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="e9130-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="e9130-113">[in] Una matriz de otros métodos asociados a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e9130-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="e9130-114">Finalizar esta matriz con un `mdTokenNil` token.</span><span class="sxs-lookup"><span data-stu-id="e9130-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9130-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9130-115">Requirements</span></span>  
 <span data-ttu-id="e9130-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9130-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9130-117">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="e9130-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9130-118">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9130-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9130-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9130-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9130-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9130-120">See also</span></span>

- [<span data-ttu-id="e9130-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9130-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e9130-122">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9130-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
