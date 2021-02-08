---
description: 'Más información acerca de: IMetaDataEmit::D método efineProperty'
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
ms.openlocfilehash: c0c0b6009f8674a5edebf1c982e277f4ca5b185b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784039"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="a1163-103">IMetaDataEmit::DefineProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="a1163-103">IMetaDataEmit::DefineProperty Method</span></span>

<span data-ttu-id="a1163-104">Crea una definición de propiedad para el tipo especificado, con los `get` descriptores de acceso de los métodos y especificados `set` , y obtiene un token para esa definición de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a1163-104">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1163-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1163-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a1163-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1163-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="a1163-107">de Token de la clase o interfaz en la que se define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a1163-107">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="a1163-108">[in] Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a1163-108">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="a1163-109">de Marcas de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a1163-109">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="a1163-110">de Firma de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a1163-110">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="a1163-111">de Recuento de bytes de `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="a1163-111">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="a1163-112">de Tipo del valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a1163-112">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="a1163-113">de Valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a1163-113">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="a1163-114">de Recuento de caracteres (Unicode) en `pValue` .</span><span class="sxs-lookup"><span data-stu-id="a1163-114">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="a1163-115">de El método que establece el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a1163-115">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="a1163-116">de Método que obtiene el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a1163-116">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="a1163-117">de Matriz de otros métodos asociados a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a1163-117">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="a1163-118">Finalice la matriz con un `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="a1163-118">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="a1163-119">enuncia El `mdProperty` token asignado.</span><span class="sxs-lookup"><span data-stu-id="a1163-119">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1163-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1163-120">Requirements</span></span>  

 <span data-ttu-id="a1163-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1163-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1163-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a1163-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1163-123">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1163-123">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1163-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1163-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1163-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1163-125">See also</span></span>

- [<span data-ttu-id="a1163-126">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1163-126">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a1163-127">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1163-127">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
