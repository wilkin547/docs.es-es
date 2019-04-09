---
title: IMetaDataAssemblyImport::GetManifestResourceProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ba99d84686974b425bcdee0bbf4770e4843e1351
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081669"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="8d491-102">IMetaDataAssemblyImport::GetManifestResourceProps (Método)</span><span class="sxs-lookup"><span data-stu-id="8d491-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="8d491-103">Obtiene el conjunto de propiedades del recurso del manifiesto con la firma de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="8d491-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d491-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d491-104">Syntax</span></span>  
  
```  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] mdToken              *ptkImplementation,   
    [out] DWORD                *pdwOffset,   
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d491-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d491-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="8d491-106">[in] Un `mdManifestResource` token que representa el recurso para el que se va a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="8d491-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="8d491-107">[out] El nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="8d491-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="8d491-108">[in] El tamaño, en caracteres anchos, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="8d491-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="8d491-109">[out] Un puntero al número de caracteres anchos realmente devueltos en `szName`.</span><span class="sxs-lookup"><span data-stu-id="8d491-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="8d491-110">[out] Un puntero a un `mdFile` token o un `mdAssemblyRef` token que representa el archivo o ensamblado, respectivamente, que contiene el recurso.</span><span class="sxs-lookup"><span data-stu-id="8d491-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="8d491-111">[out] Un puntero a un valor que especifica el desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="8d491-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="8d491-112">[out] Un puntero a las marcas que describen los metadatos aplicados a un recurso.</span><span class="sxs-lookup"><span data-stu-id="8d491-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="8d491-113">El valor de marcas es una combinación de uno o varios [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="8d491-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d491-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d491-114">Requirements</span></span>  
 <span data-ttu-id="8d491-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d491-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d491-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="8d491-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d491-117">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d491-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="8d491-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8d491-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8d491-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d491-119">See also</span></span>

- [<span data-ttu-id="8d491-120">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d491-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
