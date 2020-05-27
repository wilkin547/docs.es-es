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
ms.openlocfilehash: b5af877c26c20bf64a27618bf24a7bce5b410419
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007785"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="81c70-102">IMetaDataEmit::SetPropertyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="81c70-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="81c70-103">Establece las características almacenadas en los metadatos de una propiedad definida por una llamada anterior al [método DefineProperty](imetadataemit-defineproperty-method.md).</span><span class="sxs-lookup"><span data-stu-id="81c70-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81c70-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81c70-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="81c70-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81c70-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="81c70-106">de Token para la propiedad que se va a cambiar.</span><span class="sxs-lookup"><span data-stu-id="81c70-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="81c70-107">de Marcas de propiedad.</span><span class="sxs-lookup"><span data-stu-id="81c70-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="81c70-108">de Tipo del valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="81c70-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="81c70-109">de Valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="81c70-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="81c70-110">de Recuento de caracteres (Unicode) en `pValue` .</span><span class="sxs-lookup"><span data-stu-id="81c70-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="81c70-111">de El método que establece el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="81c70-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="81c70-112">de Método que obtiene el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="81c70-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="81c70-113">de Matriz de otros métodos asociados a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="81c70-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="81c70-114">Termine esta matriz con un `mdTokenNil` token.</span><span class="sxs-lookup"><span data-stu-id="81c70-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81c70-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81c70-115">Requirements</span></span>  
 <span data-ttu-id="81c70-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81c70-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81c70-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="81c70-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="81c70-118">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="81c70-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81c70-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81c70-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c70-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="81c70-120">See also</span></span>

- [<span data-ttu-id="81c70-121">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="81c70-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="81c70-122">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="81c70-122">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
