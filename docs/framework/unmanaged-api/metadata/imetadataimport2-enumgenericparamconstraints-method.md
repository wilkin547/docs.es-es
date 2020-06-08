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
ms.openlocfilehash: af226f9317b67b23e03d06614ed5b9c956939c22
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503424"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="340a4-102">IMetaDataImport2::EnumGenericParamConstraints (Método)</span><span class="sxs-lookup"><span data-stu-id="340a4-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="340a4-103">Obtiene un enumerador para una matriz de restricciones de parámetros genéricos asociada al parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="340a4-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="340a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="340a4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="340a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="340a4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="340a4-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="340a4-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="340a4-107">de   Token que representa el parámetro genérico cuyas restricciones se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="340a4-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="340a4-108">enuncia Matriz de restricciones de parámetro genérico que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="340a4-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="340a4-109">de   Número máximo solicitado de tokens que se van a colocar en `rGenericParamConstraints` .</span><span class="sxs-lookup"><span data-stu-id="340a4-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="340a4-110">enuncia Puntero al número de tokens colocados en `rGenericParamConstraints` .</span><span class="sxs-lookup"><span data-stu-id="340a4-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="340a4-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="340a4-111">Return Value</span></span>  
  
|<span data-ttu-id="340a4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="340a4-112">HRESULT</span></span>|<span data-ttu-id="340a4-113">Description</span><span class="sxs-lookup"><span data-stu-id="340a4-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="340a4-114">`EnumGenericParameterConstraints`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="340a4-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="340a4-115">`phEnum`no tiene elementos de miembro.</span><span class="sxs-lookup"><span data-stu-id="340a4-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="340a4-116">En este caso, `pcGenericParameterConstraints` se establece en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="340a4-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="340a4-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="340a4-117">Requirements</span></span>  
 <span data-ttu-id="340a4-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="340a4-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="340a4-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="340a4-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="340a4-120">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="340a4-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="340a4-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="340a4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="340a4-122">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="340a4-122">See also</span></span>

- [<span data-ttu-id="340a4-123">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="340a4-123">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="340a4-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="340a4-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
