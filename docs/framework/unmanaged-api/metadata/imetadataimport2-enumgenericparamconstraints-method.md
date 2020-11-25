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
ms.openlocfilehash: 27c3ec349cf6c83f6783e252e6c5af5e99fa4b37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702841"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="04396-102">IMetaDataImport2::EnumGenericParamConstraints (Método)</span><span class="sxs-lookup"><span data-stu-id="04396-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>

<span data-ttu-id="04396-103">Obtiene un enumerador para una matriz de restricciones de parámetros genéricos asociada al parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="04396-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04396-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04396-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04396-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04396-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="04396-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="04396-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="04396-107">de   Token que representa el parámetro genérico cuyas restricciones se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="04396-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="04396-108">enuncia Matriz de restricciones de parámetro genérico que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="04396-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="04396-109">de   Número máximo solicitado de tokens que se van a colocar en `rGenericParamConstraints` .</span><span class="sxs-lookup"><span data-stu-id="04396-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="04396-110">enuncia Puntero al número de tokens colocados en `rGenericParamConstraints` .</span><span class="sxs-lookup"><span data-stu-id="04396-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04396-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="04396-111">Return Value</span></span>  
  
|<span data-ttu-id="04396-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04396-112">HRESULT</span></span>|<span data-ttu-id="04396-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="04396-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="04396-114">`EnumGenericParameterConstraints` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="04396-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="04396-115">`phEnum` no tiene elementos de miembro.</span><span class="sxs-lookup"><span data-stu-id="04396-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="04396-116">En este caso, `pcGenericParameterConstraints` se establece en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="04396-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04396-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04396-117">Requirements</span></span>  

 <span data-ttu-id="04396-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04396-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04396-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="04396-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="04396-120">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04396-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="04396-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04396-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04396-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04396-122">See also</span></span>

- [<span data-ttu-id="04396-123">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04396-123">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="04396-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04396-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
