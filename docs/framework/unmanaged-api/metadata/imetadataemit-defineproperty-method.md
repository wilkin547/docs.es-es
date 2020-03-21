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
ms.openlocfilehash: eb3ecbf39376e7126b5ec93a26badcbf5076d1db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175790"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="cd5bd-102">IMetaDataEmit::DefineProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="cd5bd-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="cd5bd-103">Crea una definición de propiedad para el `get` `set` tipo especificado, con los descriptores de acceso especificados y de método, y obtiene un token a esa definición de propiedad.</span><span class="sxs-lookup"><span data-stu-id="cd5bd-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd5bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd5bd-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="cd5bd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd5bd-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="cd5bd-106">[en] El token para la clase o interfaz en la que se está definiendo la propiedad.</span><span class="sxs-lookup"><span data-stu-id="cd5bd-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="cd5bd-107">[in] Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="cd5bd-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="cd5bd-108">[en] Las marcas de propiedad.</span><span class="sxs-lookup"><span data-stu-id="cd5bd-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="cd5bd-109">[en] La firma de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="cd5bd-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="cd5bd-110">[en] El recuento de `pvSig`bytes en .</span><span class="sxs-lookup"><span data-stu-id="cd5bd-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="cd5bd-111">[en] El tipo del valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="cd5bd-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="cd5bd-112">[en] El valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="cd5bd-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="cd5bd-113">[en] El recuento de caracteres `pValue`(Unicode) en .</span><span class="sxs-lookup"><span data-stu-id="cd5bd-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="cd5bd-114">[en] El método que establece el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="cd5bd-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="cd5bd-115">[en] El método que obtiene el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="cd5bd-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="cd5bd-116">[en] Matriz de otros métodos asociados a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="cd5bd-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="cd5bd-117">Termine la matriz `mdTokenNil`con un archivo .</span><span class="sxs-lookup"><span data-stu-id="cd5bd-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="cd5bd-118">[fuera] El `mdProperty` token asignado.</span><span class="sxs-lookup"><span data-stu-id="cd5bd-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd5bd-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd5bd-119">Requirements</span></span>  
 <span data-ttu-id="cd5bd-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd5bd-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd5bd-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cd5bd-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cd5bd-122">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cd5bd-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd5bd-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd5bd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd5bd-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd5bd-124">See also</span></span>

- [<span data-ttu-id="cd5bd-125">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd5bd-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="cd5bd-126">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd5bd-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
