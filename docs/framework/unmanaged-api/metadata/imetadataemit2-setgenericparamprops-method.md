---
title: IMetaDataEmit2::SetGenericParamProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4c998d70fa5dd41ab4c1656f129bb77767a8ab97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574630"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="6dbc5-102">IMetaDataEmit2::SetGenericParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="6dbc5-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="6dbc5-103">Establece los valores de propiedad de la definición de parámetro genérico al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dbc5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6dbc5-104">Syntax</span></span>  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6dbc5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6dbc5-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="6dbc5-106">[in] El token para la definición de parámetro genérico para el que se va a establecer los valores.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="6dbc5-107">[in] Un valor de la [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeración que describe el tipo del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="6dbc5-108">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-108">[in] Optional.</span></span> <span data-ttu-id="6dbc5-109">El nombre del parámetro que se va a establecer los valores.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="6dbc5-110">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="6dbc5-111">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-111">[in] Optional.</span></span> <span data-ttu-id="6dbc5-112">Una matriz terminada en cero de restricciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="6dbc5-113">Miembros de la matriz deben ser un `mdTypeDef`, `mdTypeRef`, o `mdTypeSpec` token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dbc5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6dbc5-114">Requirements</span></span>  
 <span data-ttu-id="6dbc5-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dbc5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dbc5-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="6dbc5-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6dbc5-117">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6dbc5-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6dbc5-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dbc5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dbc5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dbc5-119">See also</span></span>
- [<span data-ttu-id="6dbc5-120">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6dbc5-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="6dbc5-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6dbc5-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
