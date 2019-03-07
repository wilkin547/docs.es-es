---
title: IMetaDataImport2::EnumGenericParamConstraints (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParamConstraints
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cdc617039ac8328e0153abc7cc3752c54060a8c4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481474"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="6c4b2-102">IMetaDataImport2::EnumGenericParamConstraints (Método)</span><span class="sxs-lookup"><span data-stu-id="6c4b2-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="6c4b2-103">Obtiene un enumerador para una matriz de restricciones de parámetros genéricos asociados con el parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="6c4b2-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c4b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c4b2-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c4b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6c4b2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6c4b2-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="6c4b2-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="6c4b2-107">[in]   Un token que representa el parámetro genérico cuyos restricciones son que hay que enumerar.</span><span class="sxs-lookup"><span data-stu-id="6c4b2-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="6c4b2-108">[out] Matriz de restricciones de parámetros genéricos a enumerar.</span><span class="sxs-lookup"><span data-stu-id="6c4b2-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6c4b2-109">[in]   El número máximo solicitado de tokens para colocar en `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="6c4b2-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="6c4b2-110">[out] Un puntero al número de tokens se coloca en `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="6c4b2-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c4b2-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6c4b2-111">Return Value</span></span>  
  
|<span data-ttu-id="6c4b2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c4b2-112">HRESULT</span></span>|<span data-ttu-id="6c4b2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c4b2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6c4b2-114">`EnumGenericParameterConstraints` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6c4b2-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6c4b2-115">`phEnum` no tiene ningún elemento de miembro.</span><span class="sxs-lookup"><span data-stu-id="6c4b2-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="6c4b2-116">En este caso, `pcGenericParameterConstraints` se establece en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="6c4b2-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c4b2-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c4b2-117">Requirements</span></span>  
 <span data-ttu-id="6c4b2-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c4b2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c4b2-119">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="6c4b2-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6c4b2-120">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c4b2-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6c4b2-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c4b2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c4b2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c4b2-122">See also</span></span>
- [<span data-ttu-id="6c4b2-123">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c4b2-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="6c4b2-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c4b2-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
