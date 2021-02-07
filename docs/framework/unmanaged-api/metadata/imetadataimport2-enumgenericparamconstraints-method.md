---
description: 'Más información sobre: IMetaDataImport2:: Enumgenericparamconstraints ((método)'
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
ms.openlocfilehash: d7ee44059796a943411750b66f5b45034f871a0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677553"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="ded33-103">IMetaDataImport2::EnumGenericParamConstraints (Método)</span><span class="sxs-lookup"><span data-stu-id="ded33-103">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>

<span data-ttu-id="ded33-104">Obtiene un enumerador para una matriz de restricciones de parámetros genéricos asociada al parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="ded33-104">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ded33-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ded33-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ded33-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ded33-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="ded33-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="ded33-107">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="ded33-108">de   Token que representa el parámetro genérico cuyas restricciones se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="ded33-108">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="ded33-109">enuncia Matriz de restricciones de parámetro genérico que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="ded33-109">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ded33-110">de   Número máximo solicitado de tokens que se van a colocar en `rGenericParamConstraints` .</span><span class="sxs-lookup"><span data-stu-id="ded33-110">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="ded33-111">enuncia Puntero al número de tokens colocados en `rGenericParamConstraints` .</span><span class="sxs-lookup"><span data-stu-id="ded33-111">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ded33-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ded33-112">Return Value</span></span>  
  
|<span data-ttu-id="ded33-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ded33-113">HRESULT</span></span>|<span data-ttu-id="ded33-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="ded33-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ded33-115">`EnumGenericParameterConstraints` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ded33-115">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ded33-116">`phEnum` no tiene elementos de miembro.</span><span class="sxs-lookup"><span data-stu-id="ded33-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="ded33-117">En este caso, `pcGenericParameterConstraints` se establece en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="ded33-117">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ded33-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ded33-118">Requirements</span></span>  

 <span data-ttu-id="ded33-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ded33-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ded33-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ded33-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ded33-121">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ded33-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ded33-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ded33-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ded33-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ded33-123">See also</span></span>

- [<span data-ttu-id="ded33-124">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ded33-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="ded33-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ded33-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
