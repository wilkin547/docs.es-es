---
title: IMetaDataImport2::EnumGenericParams (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
ms.openlocfilehash: 55709e79cd8bdb36fe1e32ee8a699fccb1b1bbc8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175309"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="8ea1e-102">IMetaDataImport2::EnumGenericParams (Método)</span><span class="sxs-lookup"><span data-stu-id="8ea1e-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="8ea1e-103">Obtiene un enumerador para una matriz de tokens de parámetro genérico asociados con el token TypeDef o MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="8ea1e-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ea1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ea1e-104">Syntax</span></span>  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],
   [in]  ULONG            cMax,
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ea1e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8ea1e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8ea1e-106">[adentro, fuera] Un puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="8ea1e-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="8ea1e-107">[en] El token TypeDef o MethodDef cuyos parámetros genéricos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="8ea1e-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="8ea1e-108">[fuera] Matriz de parámetros genéricos que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="8ea1e-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8ea1e-109">[en] El número máximo solicitado de `rGenericParams`tokens para colocar en .</span><span class="sxs-lookup"><span data-stu-id="8ea1e-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="8ea1e-110">[fuera] El número devuelto de `rGenericParams`tokens colocados en .</span><span class="sxs-lookup"><span data-stu-id="8ea1e-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ea1e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8ea1e-111">Return Value</span></span>  
  
|<span data-ttu-id="8ea1e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ea1e-112">HRESULT</span></span>|<span data-ttu-id="8ea1e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ea1e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8ea1e-114">`EnumGenericParams`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="8ea1e-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8ea1e-115">`phEnum`no tiene elementos miembro.</span><span class="sxs-lookup"><span data-stu-id="8ea1e-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="8ea1e-116">En este `pcGenericParams` caso, se establece en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="8ea1e-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8ea1e-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ea1e-117">Requirements</span></span>  
 <span data-ttu-id="8ea1e-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ea1e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ea1e-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8ea1e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ea1e-120">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8ea1e-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ea1e-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ea1e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ea1e-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ea1e-122">See also</span></span>

- [<span data-ttu-id="8ea1e-123">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8ea1e-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="8ea1e-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8ea1e-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
