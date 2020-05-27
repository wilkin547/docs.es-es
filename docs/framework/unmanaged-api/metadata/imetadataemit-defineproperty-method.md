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
ms.openlocfilehash: 479cb25ad8e1c263d3539a4203ac5bea781eb931
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009384"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="9404c-102">IMetaDataEmit::DefineProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="9404c-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="9404c-103">Crea una definición de propiedad para el tipo especificado, con los `get` descriptores de acceso de los métodos y especificados `set` , y obtiene un token para esa definición de propiedad.</span><span class="sxs-lookup"><span data-stu-id="9404c-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9404c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9404c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="9404c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9404c-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="9404c-106">de Token de la clase o interfaz en la que se define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9404c-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="9404c-107">[in] Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9404c-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="9404c-108">de Marcas de propiedad.</span><span class="sxs-lookup"><span data-stu-id="9404c-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="9404c-109">de Firma de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9404c-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="9404c-110">de Recuento de bytes de `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="9404c-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="9404c-111">de Tipo del valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9404c-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="9404c-112">de Valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9404c-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="9404c-113">de Recuento de caracteres (Unicode) en `pValue` .</span><span class="sxs-lookup"><span data-stu-id="9404c-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="9404c-114">de El método que establece el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="9404c-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="9404c-115">de Método que obtiene el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="9404c-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="9404c-116">de Matriz de otros métodos asociados a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9404c-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="9404c-117">Finalice la matriz con un `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="9404c-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="9404c-118">enuncia El `mdProperty` token asignado.</span><span class="sxs-lookup"><span data-stu-id="9404c-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9404c-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9404c-119">Requirements</span></span>  
 <span data-ttu-id="9404c-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9404c-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9404c-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9404c-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9404c-122">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9404c-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9404c-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9404c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9404c-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9404c-124">See also</span></span>

- [<span data-ttu-id="9404c-125">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9404c-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9404c-126">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9404c-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
