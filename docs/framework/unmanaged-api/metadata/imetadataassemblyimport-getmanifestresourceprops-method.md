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
ms.openlocfilehash: e47b1807e51427487d6af2f96ff5af437c4653eb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760949"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="5794f-102">IMetaDataAssemblyImport::GetManifestResourceProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5794f-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="5794f-103">Obtiene el conjunto de propiedades del recurso del manifiesto con la firma de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="5794f-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5794f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5794f-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="5794f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5794f-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="5794f-106">[in] Un `mdManifestResource` token que representa el recurso para el que se va a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="5794f-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="5794f-107">[out] El nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="5794f-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5794f-108">[in] El tamaño, en caracteres anchos, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="5794f-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="5794f-109">[out] Un puntero al número de caracteres anchos realmente devueltos en `szName`.</span><span class="sxs-lookup"><span data-stu-id="5794f-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="5794f-110">[out] Un puntero a un `mdFile` token o un `mdAssemblyRef` token que representa el archivo o ensamblado, respectivamente, que contiene el recurso.</span><span class="sxs-lookup"><span data-stu-id="5794f-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="5794f-111">[out] Un puntero a un valor que especifica el desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="5794f-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="5794f-112">[out] Un puntero a las marcas que describen los metadatos aplicados a un recurso.</span><span class="sxs-lookup"><span data-stu-id="5794f-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="5794f-113">El valor de marcas es una combinación de uno o varios [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="5794f-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5794f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5794f-114">Requirements</span></span>  
 <span data-ttu-id="5794f-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5794f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5794f-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="5794f-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5794f-117">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5794f-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5794f-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5794f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5794f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5794f-119">See also</span></span>

- [<span data-ttu-id="5794f-120">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5794f-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
