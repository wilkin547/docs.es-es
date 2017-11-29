---
title: "IMetaDataImport2::GetGenericParamProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetGenericParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: af6ab8fd6e941f5219c1aad2946479dda0b64264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="fdbe7-102">IMetaDataImport2::GetGenericParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="fdbe7-102">IMetaDataImport2::GetGenericParamProps Method</span></span>
<span data-ttu-id="fdbe7-103">Obtiene los metadatos asociados con el parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="fdbe7-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdbe7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdbe7-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fdbe7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fdbe7-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="fdbe7-106">[in] El token que representa el parámetro genérico para el que se va a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="fdbe7-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="fdbe7-107">[out] La posición ordinal de la `Type` parámetro en el constructor o método primario.</span><span class="sxs-lookup"><span data-stu-id="fdbe7-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="fdbe7-108">[out] Un valor de la [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeración que describe el `Type` para el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="fdbe7-108">[out] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="fdbe7-109">[out] Token de TypeDef o MethodDef que representa el propietario del parámetro.</span><span class="sxs-lookup"><span data-stu-id="fdbe7-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="fdbe7-110">[out] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="fdbe7-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="fdbe7-111">[out] El nombre del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="fdbe7-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="fdbe7-112">[in] El tamaño de la `wzName` búfer.</span><span class="sxs-lookup"><span data-stu-id="fdbe7-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="fdbe7-113">[out] El tamaño devuelto del nombre, en caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="fdbe7-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdbe7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fdbe7-114">Requirements</span></span>  
 <span data-ttu-id="fdbe7-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdbe7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdbe7-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fdbe7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fdbe7-117">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fdbe7-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fdbe7-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdbe7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdbe7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdbe7-119">See Also</span></span>  
 [<span data-ttu-id="fdbe7-120">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fdbe7-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="fdbe7-121">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fdbe7-121">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
