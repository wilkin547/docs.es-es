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
ms.openlocfilehash: dc6375f3e2cff1a744a8ff2e6a6adab27bbf8af3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177478"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="290d3-102">IMetaDataEmit::SetPropertyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="290d3-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="290d3-103">Establece las características almacenadas en metadatos para una propiedad definida por una llamada anterior al [método DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span><span class="sxs-lookup"><span data-stu-id="290d3-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="290d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="290d3-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="290d3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="290d3-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="290d3-106">[en] El token de la propiedad que se va a cambiar</span><span class="sxs-lookup"><span data-stu-id="290d3-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="290d3-107">[en] Marcas de propiedad.</span><span class="sxs-lookup"><span data-stu-id="290d3-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="290d3-108">[en] El tipo del valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="290d3-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="290d3-109">[en] El valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="290d3-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="290d3-110">[en] El recuento de caracteres `pValue`(Unicode) en .</span><span class="sxs-lookup"><span data-stu-id="290d3-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="290d3-111">[en] El método que establece el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="290d3-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="290d3-112">[en] El método que obtiene el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="290d3-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="290d3-113">[en] Matriz de otros métodos asociados a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="290d3-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="290d3-114">Termine esta matriz `mdTokenNil` con un token.</span><span class="sxs-lookup"><span data-stu-id="290d3-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="290d3-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="290d3-115">Requirements</span></span>  
 <span data-ttu-id="290d3-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="290d3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="290d3-117">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="290d3-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="290d3-118">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="290d3-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="290d3-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="290d3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="290d3-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="290d3-120">See also</span></span>

- [<span data-ttu-id="290d3-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="290d3-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="290d3-122">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="290d3-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
