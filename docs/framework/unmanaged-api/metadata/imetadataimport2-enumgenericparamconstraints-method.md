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
ms.openlocfilehash: d1683965193801dbdee038ab06366178891fd978
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426725"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="efd8f-102">IMetaDataImport2::EnumGenericParamConstraints (Método)</span><span class="sxs-lookup"><span data-stu-id="efd8f-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="efd8f-103">Obtiene un enumerador para una matriz de restricciones de parámetros genéricos asociada al parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="efd8f-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efd8f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efd8f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efd8f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="efd8f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="efd8f-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="efd8f-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="efd8f-107">de   Token que representa el parámetro genérico cuyas restricciones se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="efd8f-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="efd8f-108">enuncia Matriz de restricciones de parámetro genérico que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="efd8f-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="efd8f-109">de   Número máximo solicitado de tokens que se van a colocar en `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="efd8f-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="efd8f-110">enuncia Puntero al número de tokens colocados en `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="efd8f-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efd8f-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="efd8f-111">Return Value</span></span>  
  
|<span data-ttu-id="efd8f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="efd8f-112">HRESULT</span></span>|<span data-ttu-id="efd8f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="efd8f-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="efd8f-114">`EnumGenericParameterConstraints` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="efd8f-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="efd8f-115">`phEnum` no tiene elementos de miembro.</span><span class="sxs-lookup"><span data-stu-id="efd8f-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="efd8f-116">En este caso, `pcGenericParameterConstraints` se establece en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="efd8f-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="efd8f-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="efd8f-117">Requirements</span></span>  
 <span data-ttu-id="efd8f-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efd8f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efd8f-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="efd8f-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="efd8f-120">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="efd8f-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="efd8f-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efd8f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efd8f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="efd8f-122">See also</span></span>

- [<span data-ttu-id="efd8f-123">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="efd8f-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="efd8f-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="efd8f-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
