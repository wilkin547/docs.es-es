---
description: 'Más información sobre: IMetaDataImport2:: Enumgenericparams ((método)'
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
ms.openlocfilehash: 9d4e9d163da07ec4a3af1aa628b8b6ec4b2338fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720961"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="3cb52-103">IMetaDataImport2::EnumGenericParams (Método)</span><span class="sxs-lookup"><span data-stu-id="3cb52-103">IMetaDataImport2::EnumGenericParams Method</span></span>

<span data-ttu-id="3cb52-104">Obtiene un enumerador para una matriz de tokens de parámetro genéricos asociados al token de TypeDef o MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="3cb52-104">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cb52-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cb52-105">Syntax</span></span>  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],
   [in]  ULONG            cMax,
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cb52-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3cb52-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="3cb52-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="3cb52-107">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="3cb52-108">de El token TypeDef o MethodDef cuyos parámetros genéricos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="3cb52-108">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="3cb52-109">enuncia Matriz de parámetros genéricos que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="3cb52-109">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3cb52-110">de Número máximo solicitado de tokens que se van a colocar en `rGenericParams` .</span><span class="sxs-lookup"><span data-stu-id="3cb52-110">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="3cb52-111">enuncia Número devuelto de tokens colocados en `rGenericParams` .</span><span class="sxs-lookup"><span data-stu-id="3cb52-111">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3cb52-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3cb52-112">Return Value</span></span>  
  
|<span data-ttu-id="3cb52-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3cb52-113">HRESULT</span></span>|<span data-ttu-id="3cb52-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cb52-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3cb52-115">`EnumGenericParams` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3cb52-115">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3cb52-116">`phEnum` no tiene elementos de miembro.</span><span class="sxs-lookup"><span data-stu-id="3cb52-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="3cb52-117">En este caso, `pcGenericParams` se establece en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="3cb52-117">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3cb52-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cb52-118">Requirements</span></span>  

 <span data-ttu-id="3cb52-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cb52-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cb52-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3cb52-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3cb52-121">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3cb52-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3cb52-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cb52-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb52-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cb52-123">See also</span></span>

- [<span data-ttu-id="3cb52-124">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3cb52-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="3cb52-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3cb52-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
