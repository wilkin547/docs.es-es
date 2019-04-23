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
ms.openlocfilehash: 4daf24c1712b18d933da702e9e1ef1cbdbfc3639
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081910"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="ee709-102">IMetaDataEmit2::SetGenericParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="ee709-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="ee709-103">Establece los valores de propiedad de la definición de parámetro genérico al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="ee709-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee709-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee709-104">Syntax</span></span>  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee709-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ee709-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="ee709-106">[in] El token para la definición de parámetro genérico para el que se va a establecer los valores.</span><span class="sxs-lookup"><span data-stu-id="ee709-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="ee709-107">[in] Un valor de la [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeración que describe el tipo del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="ee709-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="ee709-108">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="ee709-108">[in] Optional.</span></span> <span data-ttu-id="ee709-109">El nombre del parámetro que se va a establecer los valores.</span><span class="sxs-lookup"><span data-stu-id="ee709-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="ee709-110">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="ee709-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="ee709-111">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="ee709-111">[in] Optional.</span></span> <span data-ttu-id="ee709-112">Una matriz terminada en cero de restricciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="ee709-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="ee709-113">Miembros de la matriz deben ser un `mdTypeDef`, `mdTypeRef`, o `mdTypeSpec` token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="ee709-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee709-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee709-114">Requirements</span></span>  
 <span data-ttu-id="ee709-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee709-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee709-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="ee709-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee709-117">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ee709-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee709-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee709-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee709-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee709-119">See also</span></span>

- [<span data-ttu-id="ee709-120">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee709-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="ee709-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee709-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
