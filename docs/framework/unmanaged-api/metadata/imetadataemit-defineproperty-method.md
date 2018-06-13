---
title: IMetaDataEmit::DefineProperty (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5c250a577f2ccdbbfefb35225b880c0e4317db36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448112"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="efaf9-102">IMetaDataEmit::DefineProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="efaf9-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="efaf9-103">Crea una definición de propiedad para el tipo especificado, con los valores especificados `get` y `set` descriptores de acceso de método y obtiene un símbolo (token) a esa definición de propiedad.</span><span class="sxs-lookup"><span data-stu-id="efaf9-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efaf9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efaf9-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="efaf9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="efaf9-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="efaf9-106">[in] El token de clase o interfaz en la que se está definiendo la propiedad.</span><span class="sxs-lookup"><span data-stu-id="efaf9-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="efaf9-107">[in] El nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="efaf9-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="efaf9-108">[in] Las marcas de propiedad.</span><span class="sxs-lookup"><span data-stu-id="efaf9-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="efaf9-109">[in] La firma de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="efaf9-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="efaf9-110">[in] El recuento de bytes en `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="efaf9-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="efaf9-111">[in] El tipo de valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="efaf9-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="efaf9-112">[in] El valor predeterminado para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="efaf9-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="efaf9-113">[in] El recuento de (Unicode) caracteres de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="efaf9-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="efaf9-114">[in] El método que establece el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="efaf9-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="efaf9-115">[in] El método que obtiene el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="efaf9-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="efaf9-116">[in] Una matriz de otros métodos asociados a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="efaf9-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="efaf9-117">Finalice la matriz con un `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="efaf9-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="efaf9-118">[out] El `mdProperty` token asignado.</span><span class="sxs-lookup"><span data-stu-id="efaf9-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efaf9-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="efaf9-119">Requirements</span></span>  
 <span data-ttu-id="efaf9-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efaf9-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efaf9-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="efaf9-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="efaf9-122">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="efaf9-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="efaf9-123">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efaf9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efaf9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="efaf9-124">See Also</span></span>  
 [<span data-ttu-id="efaf9-125">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="efaf9-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="efaf9-126">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="efaf9-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
