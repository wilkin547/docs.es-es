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
ms.openlocfilehash: 093e3edf0a3c06222ebc56a4876fca08d1b7578f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490736"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="09d4b-102">IMetaDataImport2::EnumGenericParams (Método)</span><span class="sxs-lookup"><span data-stu-id="09d4b-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="09d4b-103">Obtiene un enumerador para una matriz de tokens de parámetro genéricos asociados al token de TypeDef o MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="09d4b-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09d4b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09d4b-104">Syntax</span></span>  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],
   [in]  ULONG            cMax,
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09d4b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09d4b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="09d4b-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="09d4b-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="09d4b-107">de El token TypeDef o MethodDef cuyos parámetros genéricos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="09d4b-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="09d4b-108">enuncia Matriz de parámetros genéricos que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="09d4b-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="09d4b-109">de Número máximo solicitado de tokens que se van a colocar en `rGenericParams` .</span><span class="sxs-lookup"><span data-stu-id="09d4b-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="09d4b-110">enuncia Número devuelto de tokens colocados en `rGenericParams` .</span><span class="sxs-lookup"><span data-stu-id="09d4b-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09d4b-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="09d4b-111">Return Value</span></span>  
  
|<span data-ttu-id="09d4b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09d4b-112">HRESULT</span></span>|<span data-ttu-id="09d4b-113">Description</span><span class="sxs-lookup"><span data-stu-id="09d4b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="09d4b-114">`EnumGenericParams`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="09d4b-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="09d4b-115">`phEnum`no tiene elementos de miembro.</span><span class="sxs-lookup"><span data-stu-id="09d4b-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="09d4b-116">En este caso, `pcGenericParams` se establece en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="09d4b-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09d4b-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09d4b-117">Requirements</span></span>  
 <span data-ttu-id="09d4b-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09d4b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09d4b-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="09d4b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="09d4b-120">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="09d4b-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="09d4b-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09d4b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09d4b-122">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="09d4b-122">See also</span></span>

- [<span data-ttu-id="09d4b-123">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09d4b-123">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="09d4b-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09d4b-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
