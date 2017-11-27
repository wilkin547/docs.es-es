---
title: "IMetaDataEmit::DefineProperty (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineProperty
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fc0403fd51f028510eb60d93ff96fc7d05606366
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="f3e57-102">IMetaDataEmit::DefineProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="f3e57-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="f3e57-103">Crea una definición de propiedad para el tipo especificado, con los valores especificados `get` y `set` descriptores de acceso de método y obtiene un símbolo (token) a esa definición de propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3e57-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3e57-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3e57-104">Syntax</span></span>  
  
```  
HRESULT DefineProperty (   
    [in]  mdTypeDef          td,   
    [in]  LPCWSTR            szProperty,   
    [in]  DWORD              dwPropFlags,   
    [in]  PCCOR_SIGNATURE    pvSig,   
    [in]  ULONG              cbSig,   
    [in]  DWORD              dwCPlusTypeFlag,   
    [in]  void const         *pValue,   
    [in]  ULONG              cchValue,   
    [in]  mdMethodDef        mdSetter,   
    [in]  mdMethodDef        mdGetter,   
    [in]  mdMethodDef        rmdOtherMethods[],   
    [out] mdProperty         *pmdProp   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3e57-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3e57-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f3e57-106">[in] El token de clase o interfaz en la que se está definiendo la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3e57-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="f3e57-107">[in] El nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3e57-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="f3e57-108">[in] Las marcas de propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3e57-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="f3e57-109">[in] La firma de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3e57-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="f3e57-110">[in] El recuento de bytes en `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="f3e57-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="f3e57-111">[in] El tipo de valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3e57-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f3e57-112">[in] El valor predeterminado para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3e57-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="f3e57-113">[in] El recuento de (Unicode) caracteres de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="f3e57-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="f3e57-114">[in] El método que establece el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3e57-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="f3e57-115">[in] El método que obtiene el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3e57-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="f3e57-116">[in] Una matriz de otros métodos asociados a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3e57-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="f3e57-117">Finalice la matriz con un `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="f3e57-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="f3e57-118">[out] El `mdProperty` token asignado.</span><span class="sxs-lookup"><span data-stu-id="f3e57-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3e57-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3e57-119">Requirements</span></span>  
 <span data-ttu-id="f3e57-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3e57-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3e57-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f3e57-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3e57-122">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f3e57-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3e57-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3e57-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3e57-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3e57-124">See Also</span></span>  
 [<span data-ttu-id="f3e57-125">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3e57-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="f3e57-126">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3e57-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
