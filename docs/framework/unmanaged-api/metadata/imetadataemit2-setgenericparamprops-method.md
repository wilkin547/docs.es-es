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
ms.openlocfilehash: 2d74ee7512f640ab906f1119f61e4998b5e882eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445692"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="9cda6-102">IMetaDataEmit2::SetGenericParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="9cda6-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="9cda6-103">Establece los valores de propiedad para la definición de parámetro genérico al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="9cda6-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cda6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9cda6-104">Syntax</span></span>  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9cda6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9cda6-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="9cda6-106">[in] El token para la definición de parámetro genérico para el que se va a establecer los valores.</span><span class="sxs-lookup"><span data-stu-id="9cda6-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="9cda6-107">[in] Un valor de la [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeración que describe el tipo del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="9cda6-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="9cda6-108">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="9cda6-108">[in] Optional.</span></span> <span data-ttu-id="9cda6-109">El nombre del parámetro para el que se va a establecer los valores.</span><span class="sxs-lookup"><span data-stu-id="9cda6-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="9cda6-110">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="9cda6-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="9cda6-111">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="9cda6-111">[in] Optional.</span></span> <span data-ttu-id="9cda6-112">Una matriz terminada en cero de restricciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="9cda6-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="9cda6-113">Miembros de la matriz deben ser un `mdTypeDef`, `mdTypeRef`, o `mdTypeSpec` token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="9cda6-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cda6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9cda6-114">Requirements</span></span>  
 <span data-ttu-id="9cda6-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cda6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cda6-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9cda6-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9cda6-117">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9cda6-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9cda6-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cda6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cda6-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9cda6-119">See Also</span></span>  
 [<span data-ttu-id="9cda6-120">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9cda6-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="9cda6-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9cda6-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
