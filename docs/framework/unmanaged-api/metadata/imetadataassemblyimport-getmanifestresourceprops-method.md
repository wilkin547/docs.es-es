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
ms.openlocfilehash: d87d0d46ede65cf44c84edba92fe246174088a4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177655"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="48055-102">IMetaDataAssemblyImport::GetManifestResourceProps (Método)</span><span class="sxs-lookup"><span data-stu-id="48055-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="48055-103">Obtiene el conjunto de propiedades del recurso de manifiesto con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="48055-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48055-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48055-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="48055-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48055-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="48055-106">[en] Un `mdManifestResource` token que representa el recurso para el que se obtienen las propiedades.</span><span class="sxs-lookup"><span data-stu-id="48055-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="48055-107">[fuera] El nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="48055-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="48055-108">[en] El tamaño, en caracteres `szName`anchos, de .</span><span class="sxs-lookup"><span data-stu-id="48055-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="48055-109">[fuera] Un puntero al número de caracteres `szName`anchos realmente devueltos en .</span><span class="sxs-lookup"><span data-stu-id="48055-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="48055-110">[fuera] Puntero a `mdFile` un token `mdAssemblyRef` o un token que representa el archivo o ensamblado, respectivamente, que contiene el recurso.</span><span class="sxs-lookup"><span data-stu-id="48055-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="48055-111">[fuera] Puntero a un valor que especifica el desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="48055-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="48055-112">[fuera] Puntero a marcas que describen los metadatos aplicados a un recurso.</span><span class="sxs-lookup"><span data-stu-id="48055-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="48055-113">El valor flags es una combinación de uno o varios [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="48055-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48055-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48055-114">Requirements</span></span>  
 <span data-ttu-id="48055-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48055-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48055-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="48055-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="48055-117">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="48055-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="48055-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48055-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48055-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48055-119">See also</span></span>

- [<span data-ttu-id="48055-120">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48055-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
