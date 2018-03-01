---
title: "IMetaDataEmit::SetPropertyProps (Método)"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 47bbd703c0b1d1b2038b4a6e5dc3aa677e02babe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="068d4-102">IMetaDataEmit::SetPropertyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="068d4-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="068d4-103">Establece las características que se almacenan en los metadatos para una propiedad definida por una llamada anterior a [método DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span><span class="sxs-lookup"><span data-stu-id="068d4-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="068d4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="068d4-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="068d4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="068d4-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="068d4-106">[in] El token para la propiedad que se va a cambiar</span><span class="sxs-lookup"><span data-stu-id="068d4-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="068d4-107">[in] Marcas de propiedad.</span><span class="sxs-lookup"><span data-stu-id="068d4-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="068d4-108">[in] El tipo de valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="068d4-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="068d4-109">[in] El valor predeterminado para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="068d4-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="068d4-110">[in] El recuento de (Unicode) caracteres de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="068d4-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="068d4-111">[in] El método que establece el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="068d4-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="068d4-112">[in] El método que obtiene el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="068d4-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="068d4-113">[in] Una matriz de otros métodos asociados a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="068d4-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="068d4-114">Finalizar esta matriz con un `mdTokenNil` símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="068d4-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="068d4-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="068d4-115">Requirements</span></span>  
 <span data-ttu-id="068d4-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="068d4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="068d4-117">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="068d4-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="068d4-118">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="068d4-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="068d4-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="068d4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="068d4-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="068d4-120">See Also</span></span>  
 [<span data-ttu-id="068d4-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="068d4-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="068d4-122">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="068d4-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
