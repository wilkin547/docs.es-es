---
title: "IMetaDataEmit2::SetGenericParamProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.SetGenericParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5de54b3d113c8d43bd004b18e0a6cb22b1051dc6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="5850e-102">IMetaDataEmit2::SetGenericParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5850e-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="5850e-103">Establece los valores de propiedad para la definición de parámetro genérico al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="5850e-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5850e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5850e-104">Syntax</span></span>  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5850e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5850e-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="5850e-106">[in] El token para la definición de parámetro genérico para el que se va a establecer los valores.</span><span class="sxs-lookup"><span data-stu-id="5850e-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="5850e-107">[in] Un valor de la [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeración que describe el tipo del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="5850e-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="5850e-108">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="5850e-108">[in] Optional.</span></span> <span data-ttu-id="5850e-109">El nombre del parámetro para el que se va a establecer los valores.</span><span class="sxs-lookup"><span data-stu-id="5850e-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="5850e-110">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="5850e-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="5850e-111">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="5850e-111">[in] Optional.</span></span> <span data-ttu-id="5850e-112">Una matriz terminada en cero de restricciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="5850e-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="5850e-113">Miembros de la matriz deben ser un `mdTypeDef`, `mdTypeRef`, o `mdTypeSpec` token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5850e-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5850e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5850e-114">Requirements</span></span>  
 <span data-ttu-id="5850e-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5850e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5850e-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5850e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5850e-117">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5850e-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5850e-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5850e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5850e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5850e-119">See Also</span></span>  
 [<span data-ttu-id="5850e-120">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5850e-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="5850e-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5850e-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
